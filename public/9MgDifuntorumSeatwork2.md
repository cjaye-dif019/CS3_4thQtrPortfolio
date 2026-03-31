# Seatwork #2 - Getting to know CSS Position and z-index.
### This seatwork will ask you to implement the different CSS position on a given code.
### short link to this .md file is: https://bit.ly/4c61P9K
#### Resources (also found in Khub week 5)
- [4 Minute Youtube Video on CSS Position](https://www.youtube.com/watch?v=YEmdHbQBCSQ)
- [CSS Position Tutorial](https://roycan.github.io/CssPositioningZIndexLab/)

### Instructions: 
1. This is individual submission in khub, but you can work with a partner.  When you submit in khub please place both your names in the submission bin.
2. Guided Activity (30 minutes), please follow what is being required.  

    - Make a copy of this .md file to your Q4 repository and name it as **SectionLNseatwork2.md** example **9LiCruzSeatwork2.md**. Place it in your q4 repository vscode local computer. Committing frequently to your Github repository.  
    - Copy the code below and paste it inside a new file (name it as SectionLNseatwork2.html). Place this file in the same location where the .md file is saved. 
    - Change the content values of the meta tags to your names for author/s and the date today for revised.
    - Please do the following tasks that will ask you to reposition HTML elements then answer the guided question for each task on the .md file. Commit changes to the .md file and to the .html file as well.
    **- This seatwork is worth 20pts and should be submitted by the end of the period** The link to [KHub submission bin](https://khub.mc.pshs.edu.ph/mod/assign/view.php?id=15481).
      - Submit the links to your .md file and .html file.

```html
<!DOCTYPE html>
<html>
<head>
  <meta name="author" content="<your names>" />
  <meta name="revised" content="<date today>" />
  <style>
    body { font-family: Arial, sans-serif; }
    .header, .footer {
      background: lightblue;
      padding: 10px;
    }
    .footer {
       opacity: 0.5;
    }
    .sidebar {
      background: lightgreen;
      width: 150px;
      height: 200px;
    }
    .content {
      background: lightyellow;
      width: 300px;
      height: 200px;
    }    
  </style>
</head>
<body>
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="content">Main Content</div>
  <div class="footer">Footer</div>
</body>
</html>
```
### Step 1 (Static vs Relative):

- Add in css ```position: relative; top: 20px; left: 20px;``` to .sidebar.

- Guided Question: What changed compared to the default static positioning? Try to give different values to top and left or you can change it to bottom, right.

  Compared to the default static position, the sidebar box moved down and to the right.
  When the value of top is increased, the element moves down, and when the value of left is increased, it moves to the right. Aside from this, when using bottom and right properties, it can be observed that it moves the opposite as well.

### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?
  
  When I scrolled the page, the footer remained in the same position on the screen. This is because of the *position: fixed property*. When this property is applied, the element stays fixed and atatched to its current position and does not move when scrolling unlike with *position: relative*.

### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?

  *position: absolute* places the element relative to its nearest positioned parent. Unlike fixed, it does not stay in place when scrolling.

### Step 4 : (Absolute)

- Add in html ```<div class="notice">Notice!</div>``` and include the css below:

```css
.notice {
    position: absolute;
    top: 60px;
    left: 400px;
    background: orange;
    padding: 10px;
    z-index: 2;
}
```

- Give .content a z-index: 1.

- Guided Question: Why does the notice appear on top of the content? What happens if you swap the z‑index values?

  The element notice appeared on top because it has a higher z-index than the element content. If you swap the values (make the z-index vaue for notice lower), the notice will go behind the element content.

- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).

      (check HTML code for changes)

    * Try to change the position of .content to relative then to fixed. What do you observed each time?
      
      relative:
        - The element stays in its normal place but can be moved slightly. It may look like it shifted depending on offsets.

      fixed:
        - The element becomes attached to the screen. It stays in place even when scrolling, and can't be moved when scrolled.

    * What do you observe on about the effect of z-index on .notice and .content boxes?

      It can be observed that the z-index controls which element appears in front or behind.
        - higher value = closer to the front
        - lower value = pushed behind

3. Please answer the following reflection questions (15 minutes)

    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)? 

      - static: elements follow normal positioning
      - relative: elements follow normal positioning but can be moved relative to its original position using the four directions
      - absolute: element is removed from its normal position and is positioned relative to its nearest positioned ancestor (or to the page) instead
      - fixed: element is positioned relative to the page, and stays in the same position when scrolling

    b. How does absolute positioning depend on its parent element?

      - This position style looks for the nearest parent with a position other than static. If there is a parent element, the element with this position style will position itself inside the parent, otherwise it will position itself relative to the page.

    c. How do you differentiate sticky from fixed (you can research on sticky)?
    
      - fixed: always in the same position regardless of scrolling
      - sticky: acts relative but sticks in place after scrolling for a while

    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.
      - If it's going to be used on a school event webpage, the navigation bar would be fixed for easier navigation and visibility. I would also use the sticky style to ensure announcements stay visible while scrolling. Lastly, I will use z-index to layer my design and to ensure important elements appear above the other contents.