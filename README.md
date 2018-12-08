# Vlocity Newport Design System

Welcome to the [Vlocity Newport Design System] brought to you by [Vlocity](https://vlocity.com).

* Tailored for building Vlocity Newport apps: Using the Newport Design System markup and CSS framework results in UIs that reflect the Vlocity Newport look and feel.
* Based on the [Salesforce Lightning Design System](https://lightningdesignsystem.com).

## Quick start

Before getting started ensure you have 

1. Clone the project with `git clone https://github.com/vlocityinc/newport-design-system.git`
2. Change into the `newport-design-system` folder using `cd newport-design-system`.
3. Run `npm install`. 
4. Run `npm start` to launch the Previewer.
5. Visit http://localhost:3003/local/preview

## Update `Path` component with UI brand guidelines
1. Navigate to `design-tokens` folder in the root directory.
2. Inside `design-tokens` -> `force-base` -> `aliases` -> `color.yml` define a new brand colors 
```
TRAINING_RED: "#D61717"
BLACK : "#000000"
```
3. Navigate to `ui` -> `components` -> `path` -> `tokens` -> `background-color.yml`, update the colors values to `TRAINING_RED` and `BLACK` to match the UX Designs provided.
4. Save your changes, you should be able to see the change in the previewer. 
5. Run `npm run-script dist` in your terminal, this will 
6. Find the `.dist` folder and zip the contents inside the folder.
7. Upload the folder to Static Resource and name it as TrainingNDS
8. Reference the folder from your Visualforce Page.
```
<apex:stylesheet value="{!URLFOR($Resource.TrainingNDS, 'assets/styles/vlocity-newport-design-system.css')}"/>
```
--- OR : Reference inside BusinessProcessComponent ---
```
strCSSFileList="[TrainingNDS:/assets/styles/vlocity-newport-design-system.css]"
```
