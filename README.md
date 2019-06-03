# VTEX Product Quantity

## Description

The VTEX Product Quantity allows the user to add to cart the specified amount of the displayed product

## Table of Contents

- [Usage](#usage)
  - [Blocks API](#blocks-api)
    - [Configuration](#configuration)
  - [Styles API](#styles-api)
    - [CSS Namespaces](#css-namespaces)

## Usage

This app uses our store builder with the blocks architecture. To know more about Store Builder [click here.](https://help.vtex.com/en/tutorial/understanding-storebuilder-and-stylesbuilder#structuring-and-configuring-our-store-with-object-object)

To use this app or override the default CSS you need import it in your dependencies on `manifest.json` file.

```json
  "dependencies": {
    "vtex.product-quantity": "1.x"
  }
```

This block may be used inside the `product-details` block.

To use it, you must declare its use in your `product-details` block array. An example of usage in a `blocks.json`:

```json
"product-details#default": {
    "blocks": [
      "breadcrumb",
      "product-name",
      "product-images",
      "product-price",
      "product-description",
      "product-specifications",
      "buy-button",
      "sku-selector",
      "shipping-simulator",
      "availability-subscriber",
      "share",
      "product-quantity"
    ],
    "props": {
      "displayVertically": true,
      "share": {
        "social": {
          "Facebook": true,
          "WhatsApp": true,
          "Twitter": false
        }
      },
      "price": {
        "labelSellingPrice": null,
        "showListPrice": true,
        "showLabels": true,
        "showInstallments": true,
        "showSavings": true
      },
      "name": {
        "showBrandName": false,
        "showSku": false,
        "showProductReference": false
      }
    }
  },
  "product-quantity": {
    "props": {
      "warningQuantityThreshold": 9999999
    }
  },
```

### Blocks API

#### Configuration

Through the Storefront, you can change the Product Quantity Selector's behavior and interface. However, you also can make in your theme app, as Store theme does.

| Prop name                  | Type     | Description                                                                                                                                                             |
| -------------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `warningQuantityThreshold` | `Number` | Only show the quantity of remaining items in stock if item available quantity is less than or equal to the value passed in this property. Default: 0 (does not appear). |

### Styles API

This app provides some CSS classes as an API for style customization.

To use this CSS API, you must add the `styles` builder and create an app styling CSS file.

1. Add the `styles` builder to your `manifest.json`:

```json
  "builders": {
    "styles": "1.x"
  }
```

2. Create a file called `vtex.product-quantity.css` inside the `styles/css` folder. Add your custom styles:

```css
.quantitySelectorContainer {
  margin-top: 10px;
}
```

#### CSS Namespaces

Below, we describe the namespaces that are defined in the Product Quantity Selector.

| Token name                   | Component                                                                                                    | Description                                           |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------- |
| `quantitySelectorContainer`  | [index](https://github.com/vtex-apps/product-quantity/blob/master/react/components/ProductQuantity/index.js) | The main container of `Product Quantity Selector`     |
| `availableQuantityContainer` | [index](https://github.com/vtex-apps/product-quantity/blob/master/react/components/ProductQuantity/index.js) | The container that wraps the available quantity view. |
