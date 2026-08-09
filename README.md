# ProfitPandit

Chrome extension for Indian e-commerce sellers — Amazon.in profit calculator (MVP).
Full plan: [BLUEPRINT.md](BLUEPRINT.md)

## Extension ko Chrome mein load kaise karein (development mode)

1. Chrome kholo → address bar mein `chrome://extensions` type karo
2. Right-top mein **Developer mode** ON karo
3. **Load unpacked** button dabao
4. Ye folder select karo: `saas-product/extension`
5. Ab koi bhi Amazon.in product page kholo (koi bhi product → uska page) —
   right side mein **ProfitPandit panel** dikhega

## Test kaise karein

1. Amazon.in par koi product kholo (e.g. koi 500–1000 rupaye wala item)
2. Panel mein apna **cost price** aur **weight** daalo
3. **Profit Nikaalo** dabao — fees ka breakdown aur final profit/loss dikhega

## Code change karne ke baad

`chrome://extensions` par jao → ProfitPandit card par **reload (↻)** icon dabao →
Amazon page refresh karo.

## Folder structure

```
extension/
  manifest.json          — extension ki config (MV3)
  content/
    selectors.js         — Amazon.in ke DOM selectors (ek jagah, easy to fix)
    fees.js              — fee structure + profit calculation
    panel.js             — floating panel UI + logic
    panel.css            — panel styling
  popup/
    popup.html           — toolbar icon click par dikhne wala popup
  icons/                 — placeholder icons (baad mein designer wale lagenge)
```

## Abhi ke known limitations (Week 1–2 ka kaam)

- Fee rates simplified hain — Amazon Seller Central ke current rate card se
  verify/expand karne hain ([BLUEPRINT.md](BLUEPRINT.md) section 3, Week 2)
- Sirf desktop layout ke selectors hain; kuch page layouts par price detect
  nahi hogi (panel manual entry offer karta hai)
- FBA vs Easy Ship ka difference abhi nahi hai — abhi Easy Ship assume karta hai
