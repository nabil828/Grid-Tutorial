# CSS Grid
FlexBox is a layout module that would help us to design a flexible responsive layout without the need of *float* CSS property.

<style>
.grid-container {
  display: grid;
  grid-gap: 10px;
  background-color: #2196F3;
  padding: 10px;
  text-align: center;
  color: black;
}
.grid-container2 {
  display: grid;
  background-color: #2196F3;
  padding: 10px;
  text-align: center;
}
.grid-item {
  background-color: rgba(255, 255, 255, 0.8);
  color:#000;
}
.grid-item2 {
  background-color: rgba(255, 255, 255, 0.8);
  color:#000;  
  border: 1px solid rgba(0, 0, 0, 0.8);
}
.item1 {
  grid-row: 1;
  grid-column: 1;
}
.item2 {
  grid-row: 1;
  grid-column: 2;
}
.item3 {
  grid-row: 1;
  grid-column: 3;
}
.item4 {
  grid-row: 2;
  grid-column: 1;
}
.item5 {
  grid-row: 2;
  grid-column: 2;
}
.item6 {
  grid-row: 2;
  grid-column: 3;
}
.item7 {
  grid-row: 3;
  grid-column: 1 / span 3;
}

.anchor-container {
  position:relative;
}
.anchor-container a {
  position:absolute;
  top:-100px;
}
</style>
<div class="grid-container" style="grid-template-areas:
    'header header header header header header'
    'menu main main main right right'
    'menu footer footer footer footer footer';">
  <div class="grid-item" style="grid-area: header"><h3>Header</h3></div>
  <div class="grid-item" style="grid-area: menu"><h3>Menu</h3></div>
  <div class="grid-item" style="grid-area: main"><h3>Main</h3></div>
  <div class="grid-item" style="grid-area: right"><h3>Right</h3></div>
  <div class="grid-item" style="grid-area: footer"><h3>Footer</h3></div>
</div>

<!-- ## How to? -->
### Flex Container
First we need to create a container with `Display: flex` - The following `article` element is a flex container.
```html
article {
             display: flex;
             background-color: white;
       }

<article>
  <p>1</p>
  <p>2</p>
  <p>3</p>
</article>
```


A Flexible Layout must have a parent element with the *display* property set to *flex*.

Direct child elements(s) of the flexible container automatically becomes flexible items.
<details>
  <summary>
    Example 1 - expand for code
  </summary>

  ```html
  <html>
      <head>
          <style>
              article{
                  display: flex;
                  background-color: white;
              }
              p{
                  color: black;
              }
              #p1{
                  background-color: #a2b9bc;
              }
              #p2{
                  background-color: #b2ad7f;
              }
              #p3{
                  background-color: #878f99;
              }
          </style>
      </head>
      <body>
          <article class="flex-container">
              <p id="p1"> Lorem ipsum dolor sit amet consectetur adipisicing elit. Natus, iusto perferendis corrupti, ex veniam incidunt quod porro placeat fuga pariatur quaerat. Quaerat sapiente dignissimos animi voluptates enim voluptate harum officia!</p>

              <p id="p2">Lorem ipsum dolor sit amet consectetur adipisicing elit. Sapiente deserunt fuga magni cupiditate nam suscipit sunt, expedita, ab facilis consectetur maxime repellendus quos exercitationem inventore rerum consequatur, maiores porro pariatur.</p>

              <p id="p3">Lorem ipsum dolor sit amet consectetur adipisicing elit. Est, doloremque. Sunt obcaecati reiciendis illo excepturi fugit mollitia libero numquam, tempora nihil ratione dolores, voluptas deserunt asperiores blanditiis enim nam ab.</p>
            </article>
      </body>
  </html>
  ```
</details>

![Example 1 image](https://cdn.discordapp.com/attachments/967913354582704228/967913370483310662/unknown.png)


---
# Flex Container Properties
- flex-direction
- flex-wrap
- flex-flow
- justify-content
- align-items
- align-content
## flex-direction
The "flex-direction: column;" stacks the flex items vertically (from top to bottom). Default value is `row`. [W3Schools Reference](https://www.w3schools.com/cssref/css3_pr_flex-direction.asp).
```css
article {
    display: flex;
    background-color: white;
    flex-direction: column;
}
```
![alternate text](https://cdn.discordapp.com/attachments/967913354582704228/967937379979636766/unknown.png)
## flex-wrap
The "flex-wrap: wrap;" specifies that the flex items will wrap if necessary. Default value is `nowrap`. [W3Schools Reference](https://www.w3schools.com/cssref/css3_pr_flex-wrap.asp).
```css
  article{
       display: flex;
       background-color: white;
       flex-wrap: wrap;

       padding: 10px;
   }
   p{
       color: black;
       width: 200px;
   }
```
-`flex-Wrap` ON
![alternate text](https://cdn.discordapp.com/attachments/967913354582704228/967940295364849724/unknown.png)
-`flex-Wrap` OFF
![alternate text](https://cdn.discordapp.com/attachments/967913354582704228/967941088390295622/unknown.png)
## flex-flow
The flex-flow property is a shorthand property for the `flex-direction` and the `flex-wrap` properties. Default value is `row nowrap`. [W3Schools Reference](https://www.w3schools.com/cssref/css3_pr_flex-flow.asp).
```css
article{
    display: flex;
    background-color: white;
    flex-flow: row nowrap;
    padding: 10px;
}
```
![alternate text](https://cdn.discordapp.com/attachments/967913354582704228/967946138487517184/unknown.png)
## justify-content
The "justify-content: center;" aligns the flex items at the center of the container. Default value is `flex-start`. [W3Schools Reference](https://www.w3schools.com/cssref/css3_pr_justify-content.asp).
```css
article {
             display: flex;
             background-color: white;
             justify-content: center;
             padding: 10px;
         }
```
![alternate text](https://cdn.discordapp.com/attachments/967913354582704228/967947642678149141/unknown.png)

## align-items
The "align-items: center;" aligns the flex items in the middle of the container.  Default value is `stretch`. [W3Schools Reference](https://www.w3schools.com/cssref/css3_pr_align-items.asp).
```css
  html, body{
       height: 100%;
   }
   article{
       height: 100%;
       display: flex;
       background-color: white;
       padding: 10px;
       align-items: center;

   }
```
![alternate text](https://cdn.discordapp.com/attachments/961661089295265946/968020007198003240/unknown.png)
## align-content
The "align-content: space-between;" displays the flex lines with equal space between them. Default value is stretch. [W3Schools Reference](https://www.w3schools.com/cssref/css3_pr_align-content.asp).
```css
        html, body{
            height: 100%;
        }
        article{
            height: 100%;
            display: flex;
            background-color: white;
            padding: 10px;
            align-content: center;
            flex-wrap: wrap;

        }
```
- with `align-content: center;`:
![alternate text](https://cdn.discordapp.com/attachments/967913354582704228/968021816822104064/unknown.png)
- without `align-content: center;` :
![alternate text](https://cdn.discordapp.com/attachments/967913354582704228/968022382541434920/unknown.png)

# In-class Exercise (5 min):
Try to use both the `justify-content` and `align-items` properties to `center` to perfectly center a flex item:
![alternate](https://cdn.discordapp.com/attachments/967913354582704228/968023164644913172/unknown.png)
---
# CSS Flex Items
Flex items are the direct child elements of a flex container.

---
## Flex Container Properties
- order
- flex-grow
- flex-shrink
- flex-basis
- flex
- align-self
### order
Use the order property to sort the flex items as you like. default value is 0.
```css
           html, body{
               height: 100%;
           }
           article{
               /* height: 100%; */
               display: flex;
               background-color: white;
               padding: 10px;
               /* align-content: center; */
               /* flex-wrap: wrap; */
               align-items: center;
               /* justify-content: center; */

           }
           p{
               color: black;
               width: 200px;
           }
           #p1{
               background-color: #a2b9bc;

           }
           #p2{
               background-color: #b2ad7f;
               order: 20;
           }
           #p3{
               background-color: #878f99;

           }
```
![alternate text](https://cdn.discordapp.com/attachments/967913354582704228/968028220366671872/unknown.png)
### flex-grow
The flex-grow property specifies how much a flex item will grow relative to the rest of the flex items.
```css
html, body{
          height: 100%;
      }
      article{
          /* height: 100%; */
          display: flex;
          background-color: white;
          padding: 10px;
          /* align-content: center; */
          /* flex-wrap: wrap; */
          align-items: center;
          /* justify-content: center; */

      }
      p{
          color: black;
          width: 200px;
      }
      #p1{
          background-color: #a2b9bc;
          /* order: 1 */
      }
      #p2{
          background-color: #b2ad7f;
          /* order: 20; */
          flex-grow: 10;
      }
      #p3{
          background-color: #878f99;
          /* order: -10; */
      }
```
![alternate text](https://cdn.discordapp.com/attachments/967913354582704228/968027833358241823/unknown.png)
### flex-shrink
The flex-shrink property specifies how much a flex item will shrink relative to the rest of the flex items. Default value is 1;

```css
article{
             /* height: 100%; */
             display: flex;
             background-color: white;
             padding: 10px;
             /* align-content: center; */
             /* flex-wrap: wrap; */
             align-items: center;
             /* justify-content: center; */

         }
         p{
             color: black;
             width: 200px;
         }
         #p1{
             background-color: #a2b9bc;

         }
         #p2{
             background-color: #b2ad7f;
             flex-shrink: 10;
         }
         #p3{
             background-color: #878f99;

         }
```
![alternate text](https://cdn.discordapp.com/attachments/967913354582704228/968028953803640852/unknown.png)

### flex-basis
The flex-basis property specifies the initial length of a flex item.
```css
          #p1{
              background-color: #a2b9bc;

          }
          #p2{
              background-color: #b2ad7f;
              flex-basis: 400px;
          }
          #p3{
              background-color: #878f99;

          }
```
![alternate](https://cdn.discordapp.com/attachments/967913354582704228/968032070276374558/unknown.png)



### flex
The `flex` property is a shorthand property for the `flex-grow`, `flex-shrink`, and `flex-basis` properties.
```css
          #p1{
               background-color: #a2b9bc;

           }
           #p2{
               background-color: #b2ad7f;
               flex: 1  1 400px;
           }
           #p3{
               background-color: #878f99;

           }
```
![alternate text](https://cdn.discordapp.com/attachments/967913354582704228/968033007288062002/unknown.png)
Note - Assigning `flex: number` will fix the `flex-grow` only.
### align-self
The `align-self` property specifies the alignment for the selected item inside the flexible container. Default is `auto`.
```css
           html, body{
               height: 100%;
           }
           article{
               height: 100%;
               display: flex;
               background-color: white;
               padding: 10px;
               /* align-content: center; */
               /* flex-wrap: wrap; */
               align-items: center;
               /* justify-content: center; */

           }
           p{
               color: black;
               width: 200px;
           }
           #p1{
               background-color: #a2b9bc;

           }
           #p2{
               background-color: #b2ad7f;
               align-self: flex-end;
           }
           #p3{
               background-color: #878f99;

           }
```

![alternate](https://cdn.discordapp.com/attachments/967913354582704228/968033723129954304/unknown.png)

---

# Responsive Flexbox
We can use CSS Media Queries to change the layout from column based to row based on big and small screens respectively.
```css
html,
     body {
         height: 100%;
     }

     article {
         /* height: 100%; */
         display: flex;
         background-color: white;
         padding: 10px;
         /* align-content: center; */
         /* flex-wrap: wrap; */
         /* align-items: center; */
         /* justify-content: center; */

     }

     p {
         color: black;
         width: 200px;
     }

     #p1 {
         background-color: #a2b9bc;


     }

     #p2 {
         background-color: #b2ad7f;

     }

     #p3 {
         background-color: #878f99;
     }

     @media (max-width: 800px) {
         article {
             flex-direction: column;
         }
         p{
              width: auto;
         }
     }
```
- Wide Screens
![alternate](https://cdn.discordapp.com/attachments/967913354582704228/968040239027351602/unknown.png)
- Small screens
![alternate](https://cdn.discordapp.com/attachments/967913354582704228/968040297508524073/unknown.png)
