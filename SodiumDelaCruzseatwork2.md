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
When I added position: relative; top: 20px; left: 20px; to the sidebar, the element moved 20px down and 20px to the right from its original position.
### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?
When I scroll the page, the footer stays at the bottom of the screen and does not move. This happens because position: fixed attaches the element to the viewport (screen) and, it ignores normal document flow. This is different from relative because relative moves based on original position, while fixed stays in a fixed spot on the screen regardless of scrolling. 
### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?
With position: absolute, the content is positioned based on its nearest positioned parent or the page if none exists. It is removed from normal document flow, and other elements behave as if it’s not there its difference from fixed is that absolute moves when you scroll unless inside a fixed container, and fixed does not move when scrolling. 
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
It has a higher z-index (2) than the content (1). If you swap them, the content will appear on top of the notice. 
- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).
    * Try to change the position of .content to relative then to fixed. What do you observed each time?
    * What do you observe on about the effect of z-index on .notice and .content boxes?
To make .notice stay at the top-right of .content, you need to make .content the positioned parent then position .notice absolutely inside it
3. Please answer the following reflection questions (15 minutes)


    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)?
  
The different CSS position values each control how elements are placed on a webpage. Static positioning is the default, where elements follow the normal document flow and cannot be adjusted using top, left, right, or bottom. Relative positioning allows an element to be moved from its original position while still keeping its space in the layout. Absolute positioning removes the element from the normal flow and places it based on its nearest positioned parent. Fixed positioning attaches the element to the viewport, meaning it stays in the same place on the screen even when the user scrolls.


    b. How does absolute positioning depend on its parent element?
    
Absolute positioning depends on its parent element because it uses the nearest ancestor with a non static position, such as relative, absolute, or fixed, as its reference point. If no such parent exists, the element will instead be positioned relative to the entire page. This is why setting a parent element’s position is important when using absolute positioning, as it controls where the child element will appear.


    c. How do you differentiate sticky from fixed (you can research on sticky)?
    
Sticky positioning differs from fixed positioning because it combines both relative and fixed behavior. A sticky element initially behaves like a relatively positioned element and scrolls along with the page. However, once it reaches a specified position, such as the top of the screen, it becomes fixed and stays in place. In contrast, a fixed element remains in the same position on the screen at all times, regardless of scrolling.


    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.
    
If I were designing a webpage for a school event, I would use positioning to highlight important information effectively. For example, I could use fixed positioning for a navigation bar or a “Register Now” button so that it remains visible while scrolling. I could use absolute positioning to place labels or announcements on top of images, such as highlighting guest speakers or event schedules. Relative positioning could help adjust elements slightly for better alignment without affecting the layout, while z-index could ensure that important notices or pop-ups appear above other content, making the page more organized and visually clear.
