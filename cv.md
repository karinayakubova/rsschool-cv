# Karina Yakubova

+7 901 712 1312\
karina.yackubova@gmail.com

In a role of technical product manager was leading a cross-functional team, worked on a trainer of programmer's skills and interactive learning mechanics, used to accomplish some experiments and researches in RnD department.

Last year and a half take a lead focus on a chatbots opportunities make value to EdTech and eCommerce, and bring positive customer experience in communication with businesses.

## Experience
### ChatBots Developer
self-employed\
dec. 2021 — current time

* Created an algorithm of onboarding for students of model school and transfer it into a chatbot. The curator of the school got one more free working day a week.

* On base of telegram's chatbot was running out a private shop for a manufacturer company producing casual medical dress. Conversion rate in order was in 4 times higher than on web site. After research of orders statistic found a time-window when their customers more likely to view items and submit orders. So I settled up data exchange with XML-feed to keep most actual info about prices and quantities on that specific popular time.

```
function getCatalog() {
  let url = "https://########/api/catalog.xml";
  let xml = UrlFetchApp.fetch(url).getContentText();
  let document = XmlService.parse(xml);
  let root = document.getRootElement();
  let shop = root.getChild('shop');

  let retArr = new Array();
  let categoryArr = ['11', '12', '21','22', '23'];
  let paramsArr = ['Size', 'Height', 'Modification', 'Color'];

  let xmlId = undefined;
  let name = undefined;
  let price = undefined;
  let quantity = undefined;
  let size = undefined;
  let height = undefined;
  let modification = undefined;
  let color = undefined;

  let offers = shop.getChild('offers').getChildren('offer');
  offers.forEach(offer => {

    let category = offer.getChild('categoryId').getValue();
    if (!categoryArr.includes(category)) { return; }

    xmlId = offer.getChild('xmlId').getText();
    name = offer.getChild('name').getText();
    price = offer.getChild('price').getValue();
    quantity = offer.getAttribute('quantity').getValue();

    let params = offer.getChildren('param');
    for (let i = 0; i < params.length; i++) {
      let attr = params[i].getAttribute('name').getValue();
      if (attr == paramsArr[0]) {
        size = params[i].getText();
      };
      if (attr == paramsArr[1]) {
        height = params[i].getText();
      };
      if (attr == paramsArr[2]) {
        modification = params[i].getText();
      };
      if (attr == paramsArr[3]) {
        color = params[i].getText();
      } else {
        continue;
      };
    };

    retArr.push([xmlId, name, price, quantity, size, height, modification, color]);
  });

  return retArr;
}
```
## Education

Higher: RSUH (Russian State University for the Humanities, Media Institute, faculty of journalism), 2014 graduate.\
Courses: GoPractice, Hexlet, Product University, Practicum.

👋 [t.me/karinayakubova](t.me/karinayakubova) | karina.yackubova@gmail.com