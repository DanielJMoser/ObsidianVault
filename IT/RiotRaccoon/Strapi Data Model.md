# Strapi Data Models

## Product Model
Fields:
- Title (Text - required)
- Description (Rich Text - required)
- Price (Decimal - required)
- SKU (Text - required, unique)
- Slug (UID - required, based on title)
- Stock (Integer - required)
- Images (Media - multiple)
- ProductStatus (Enumeration):
  - draft
  - published
  - outOfStock
- Categories (Relation with Category - many-to-many)
- Variants (Relation with ProductVariant - one-to-many)
- Reviews (Relation with Review - one-to-many)
- MetaTitle (Text)
- MetaDescription (Text)

## ProductVariant Model
Fields:
- Name (Text - required)
- SKU (Text - required, unique)
- Price (Decimal - required)
- Stock (Integer - required)
- Attributes (JSON - required)
  Example: { "size": "XL", "color": "red" }
- Product (Relation with Product - many-to-one)
- Images (Media - multiple)

## Category Model
Fields:
- Name (Text - required)
- Description (Rich Text)
- Slug (UID - required, based on name)
- Image (Media)
- Parent (Relation with Category - self-referential)
- Products (Relation with Product - many-to-many)
- MetaTitle (Text)
- MetaDescription (Text)

## Order Model
Fields:
- OrderNumber (Text - required, unique)
- OrderStatus (Enumeration - required):
  - pending
  - processing
  - shipped
  - delivered
  - cancelled
- Customer (Relation with User - one-to-one)
- Items (JSON - required)
  Example: [
    {
      "productId": "123",
      "variantId": "456",
      "quantity": 2,
      "price": 29.99
    }
  ]
- SubTotal (Decimal - required)
- Tax (Decimal - required)
- ShippingCost (Decimal - required)
- Total (Decimal - required)
- ShippingAddress (JSON - required)
  Example: {
    "street": "123 Main St",
    "city": "Boston",
    "state": "MA",
    "zip": "02108",
    "country": "USA"
  }
- BillingAddress (JSON - required)
- PaymentStatus (Enumeration - required):
  - pending
  - paid
  - failed
  - refunded
- PaymentMethod (Text - required)
- PaymentDetails (JSON)
- CreatedAt (DateTime)
- UpdatedAt (DateTime)

## Review Model
Fields:
- Rating (Integer - required, min: 1, max: 5)
- Comment (Text)
- Author (Relation with User - one-to-one)
- Product (Relation with Product - many-to-one)
- ReviewStatus (Enumeration - required):
  - pending
  - approved
  - rejected
- CreatedAt (DateTime)
- UpdatedAt (DateTime)

## Extended User Model (extends Strapi's default User)
Additional Fields:
- PhoneNumber (Text)
- DefaultShippingAddress (JSON)
- DefaultBillingAddress (JSON)
- Orders (Relation with Order - one-to-many)
- Reviews (Relation with Review - one-to-many)
- WishlistItems (Relation with Product - many-to-many)