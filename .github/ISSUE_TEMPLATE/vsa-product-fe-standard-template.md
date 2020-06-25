## VSA Product Standard FE Issue Template (WIP)

## Issue Description

## Front end tasks
- Ensure the page is styled according to design spec. 
- Ensure the back end data from API is displayed in local and review instance
- Ensure unit tests are available. 

<details> 

 <summary>Ensure your code changes are covered by E2E tests (expand)</summary>
 
 - Add E2E tests if none exist for this addition/change. 
 
 - Update existing E2E tests if this code will change functionality. 
 
 - Include axe checks, including hidden content
 
</details>

<details> 

 <summary> Run axe checks using the Chrome or Firefox browser plugin (expand)</summary>
 
- Ensure no heading levels are skipped.

- Ensure all buttons and labeled inputs use semantic HTML elements.

- Ensure all buttons, labeled elements and images are identified using HTML semantic markers or ARIA roles.

- Ensure form fields have clearly defined boundaries or outlines.

- Ensure form fields do not use placeholder text. 

- Ensure form fields have highly visible and specific error states. 

</details>

<details> 

 <summary> Test for color contrast and color blindness issues (expand) </summary>
 - All text has appropriate contrast. 

</details>

<details> 

 <summary> Zoom layouts to 400% at 1280px width (expand)</summary> 
 - Ensure no content gets focused offscreen or is hidden from view.
 
</details>

<details> 

 <summary> Test with 1 or 2 screen readers (expand)</summary> 
 
 - Ensure the page includes a skip navigation link. 
 
 - Ensure all links are properly descriptive. 
 
 - Ensure screen reader users can hear the text equivalent for each image conveying information. 

 - Ensure screen reader users can hear the text equivalent for each image button. 

 - Ensure screen reader users can hear labels and instructions for inputs. 
 
 - Ensure purely decorative images are not announced by the screenreader. 
 
</details>

<details> 

 <summary>Navigate using the keyboard only (expand)</summary> 
 
 - Ensure all links (navigation, text and/or image), form controls and page functions can be reached with the tab key in a logical order. 
 
 - Ensure all links (navigation, text and/or image), form controls and page functions can be triggered with the spacebar, enter key, or arrow keys.
 
 - Ensure all interactive elements can be reached with the tab key in a logical order 
 
 - Ensure all interactive elements can be triggered with the spacebar, enter key, or arrow keys.
 
 - Ensure focus is always visible and appears in logical order.
 
 - Ensure each interactive element has visible focus state which appears in logical order.
 

</details>

## Acceptance Criteria
- [ ] Designer comments on this issue to approve page styling 
- [ ] Unit tests pass
- [ ] E2E tests pass
- [ ] The data returned matches API response (for given user or scenario)
- [ ] All axe checks pass
- [ ] All color contrast checks pass
- [ ] All zoom testing passes
- [ ] All keyboard checks pass 
- [ ] Screenreader checks pass






 
 

