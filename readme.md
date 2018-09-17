# Shop snippet

## What is it?

The Shop snippet is a Playground experiment to show you, how easy you can use the Next API to develop your own experiments.

With the Shop snippet you can add a full functional shop to your blog or your website with only one file.

Your customers can order your products with only one click without leaving the page to a traditional checkout.

## How can i use it?

* Before you integrate the shop snippet into your document, you have to hand over a configuration object.

    * This configuration object includes the address to the next API, the access token, the product array, the currency,
      the snippets for the languages and the setting to enable or disable the payment request API.
    * Into the product array you can add unlimited number of products to your own page.
    * To do this, you have to hand over an UUID of your desired product and a button selector, to make your button to your buy button.
    * Optional you can hand over a price selector, a title selector, a description selector and a image selector.
    * With the selectors you can place the product data on your page using the classes of your html elements.
    * The product data will be loaded into your HTML elements and displayed on your page.
    * The button selector has to be a div container into which the buy button will be injected.
    * To enable the payment request API, you must set the allowPaymentRequestApi setting to true or remove the row,
      because the default setting is on true.
    * If the allowPaymentRequestApi setting is on false or the browser is not compatible with the API, 
      the shop snippet displays an checkout on the same page.
    * All configurations are optional, except for the settings: api, acces_token and products.
    * Important: In your sales channel you have to set the language to english by default.

The configuration object should look like (with all configurations):
   
       <script>
           let configuration = {
               api: 'http://localhost:8000',
               access_token: 'SWSCCEHUQ1HYDEV0RTZBT3PUBG',
               products: [{
                   uuid: '0009beaf0bf24301a464bd5dad6aa5da',
                   priceSelector: '.price1',
                   titleSelector: '.title1',
                   descriptionSelector: '.description1',
                   imageSelector: '.image1',
                   buttonSelector: '.button-container1'
               }, {
                   uuid: '06c7d82ba3564ed688a031439a408834',
                   priceSelector: '.price2',
                   titleSelector: '.title2',
                   descriptionSelector: '.description2',
                   imageSelector: '.image2',
                   buttonSelector: '.button-container2'
               }],
               currency: {
                   symbol: '€',
                   type: 'EUR'
               },
               templates: {
                   checkout: '/templates/checkout.html',
                   buyButton: '/templates/buy-button.html'
               },
               css: {
                   checkout: '/css/checkout.css',
                   buyButton: '/css/buy-button.css'
               },
               allowPaymentRequestApi: false,
               languageSnippets: {
                   error: "Error",
                   thankYouForYourOrder: 'Thank you for your order!',
                   theConnectionToTheApiFailed: 'The connection to the API failed',
                   total: 'Total',
                   vat: 'VAT',
                   withoutFirstName: 'Without first name',
                   yourGoodsWillBeDeliveredTo: 'Your goods will be delivered to: '
               }
           };
       </script>

* Now you can integrate the shop snippet.

This could look like:

        <script src="snippet.js"></script>
