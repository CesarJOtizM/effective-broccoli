# Front End project
The assignment is designed to check your coding and problem-solving skills. We are more interested in Architecture and Domain model design than in tooling setup.
What we evaluate in the code:
- Modularity- Code organization- Exception handling and logging- Writing and organizing tests- Asynchronous programming
The challenge is a basic shopping cart, it allows you to search, add, update and remove products.
Once you have all you need in your shopping cart you can complete the order and visit the thank you page.
You can see the [prototype](https://www.figma.com/proto/C1cHqoUvqWQaXmZSVKW3tA/Riqra-Challenge?node-id=0%3A3&viewport=-1360%2C66%2C0.5&scaling=min-zoom) and the [design inspector](https://www.figma.com/file/C1cHqoUvqWQaXmZSVKW3tA/Riqra-Challenge?node-id=0%3A1)
You will have to signup in Figma in order to use the inspector.
## Requirements
---
### Empty cart
At the beginning the cart is empty, the pricing panel is set to zero, the delivery date is calculated (see the **rules** section to know how to calculate it) and the complete order button is disabled.
The search box lets you find products.
[!alt text](https://user-images.githubusercontent.com/5007653/64066196-82d8ca00-cbdc-11e9-8315-cc8c0a7a4ba0.png)
### Cart with search results
When you type the name of a product, the matched results will appear in the cart panel.
The cart panel shows the results when the search box is not empty, otherwise, it shows the products already added to the cart.
From this view you can add the product using the counter component (see **rules** section).
![alt text](https://user-images.githubusercontent.com/5007653/64066195-82403380-cbdc-11e9-88bb-6638c1c161de.png)
### Cart with products
Here you can see the products added to our cart, the pricing panel updated and the complete order button enabled (see **rules** section to know when to enable the button).
Remember that you can only access the cart products if the searchbox is empty.
![alt text](https://user-images.githubusercontent.com/5007653/64066194-82403380-cbdc-11e9-8927-0cc5c83fd58a.png)
### Thank you
Once you complete the order you visit this page, it displays the order code and gives you a link to continue shopping.
![alt text](https://user-images.githubusercontent.com/5007653/64066197-82d8ca00-cbdc-11e9-8fdc-1dd5f7831915.png)
## Tools
1. Use [next.js](https://github.com/zeit/next.js/) to setup the project.2. Use Typescript.3. Use [styled-components](https://github.com/styled-components/styled-components) to style the components.4. Use [apollo-client](https://github.com/apollographql/apollo-client) as state manager with apollo link state and local resolvers. We use GraphQL in production, but we don't want you to build backend for this challenge.
### Deploy
1. Use [Heroku](https://www.heroku.com/) as platform to deploy.
## Rules
---
### Delivery date
The company delivers in 24 hours from Monday to Friday. Take this rule into account while calculating the delivery date.
For example:
A person buying on Friday, Saturday or Sunday will see Monday as the delivery date instead of Saturday.A person buying on Monday will see Tuesday as the delivery date.

![alt text](https://user-images.githubusercontent.com/5007653/64048283-edcfc580-cb36-11e9-809f-69046a3ec853.png)
### Pricing
The shipping cost is always 10% of the products cost.Taxes are 18% of the products cost.Product prices have taxes included.
Example:
if all products cost $100 the shipping cost will be $10 while taxes is $18 and the final price $110.
The shipping cost line must highlighted.
![alt text](https://user-images.githubusercontent.com/5007653/64048346-1061de80-cb37-11e9-9112-db5b23fdccdb.png)
### Complete order button
The complete order button is only enabled and has an orange color if the total price is equal or greather than $50, otherwise, the button is disabled and the order cannot be completed.
![alt text](https://user-images.githubusercontent.com/5007653/64048318-fb854b00-cb36-11e9-904d-23286f3662c2.png)
### Shopping cart products
A shopping cart product can be removed by clicking on the delete button.
![alt text](https://user-images.githubusercontent.com/5007653/64066260-f4b11380-cbdc-11e9-8c5f-9010e1099731.png)
### The Product and Counter components
> Check the behaviour in here> 
The counter component will dull the product component if opened and show two knowbs to decrease and increase the product quantity while the number in the middle gets updated as well as the pricing panel.
![alt text](https://user-images.githubusercontent.com/5007653/64066262-fa0e5e00-cbdc-11e9-9ae3-25eb1d7c042c.png)
### Empty cart
If the cart has no products and the search box is empty, an empty cart state is shown.
![alt text](https://user-images.githubusercontent.com/5007653/64048422-54ed7a00-cb37-11e9-8ede-d633477e5368.png)
### The Order code
The order code should be incremental, and must have 5 characters including the `P`.
example: for the first order the code will be `P0001` for the order 20 the code should be`P0020`.
