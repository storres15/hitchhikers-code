---
name: Fix CTAs to Bottom of Card
description: How to ensure the CTAs appear at the bottom of the product-prominentimage card.
keywords: Product-ProminentImage, HBS, CSS
dateUpdated: 10/5/2020
communityLinks: https://hitchhikers.yext.com/community/t/looking-for-css-help-on-universalstandard-cards-fixing-ctas-to-bottom-of-card/1701/2
product: Answers
categories: Frontend, Card Customizations

---
An easy way to make sure the CTAs are fixed to the bottom of the card is  to use [FlexBox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) to our advantage.

Assuming you're using the product-prominentImage card (or a forked version of it), add the following SCSS to your **answers.scss** file:

```css
// fix CTAs to the bottom of the card
.HitchhikerProductProminentImage {
  &-body {
    height: 100%;
    display: flex;
    flex-direction: column;
  }

  &-contentWrapper {
    height: 100%;
    justify-content: space-between;
  }
}
```

This accomplishes the following:

* Specifies the `.HitchhikerProductProminentImage-body` class to use `flex` and take up the full height of the card available after the image
* Allows the `.HitchhikerProductProminentImage-contentWrapper` class to take up the full height of the container, and specifies the spacing between the description & the CTAs to be `space-between`, forcing the CTAs to the end of the card.
![image|712x477](../../../Images/fix-ctas-to-bottom.png)

If you don't have a description, the following CSS may help you as well:

```scss
.HitchhikerProductProminentImage-ctasWrapper {
    margin-top: auto;
}
```

This will automatically set the top margin to fix the CTAs container to the bottom of the card. 

As always, make sure you test this across cards with different data variability and across browsers/devices.


