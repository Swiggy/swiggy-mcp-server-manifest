# Swiggy MCP Server

Order food, groceries and more through intelligent MCP server integrations.

## Supported Features

### 🍔 Swiggy Food

Your favorite restaurants delivered to your doorstep.

**Restaurant Search** - Discover restaurants by cuisine, name, or dish

**Menu Browsing** - Explore menus, prices, and item details

**Cart Management** - Add items, customize orders, and view bill breakdown

**Order Placement** - Seamlessly checkout and place food delivery orders

---

### 🛒 Instamart

10 min delivery for all your essentials at your fingertips.

**Available Tools:**

- **`get_addresses`** - Retrieves user's saved delivery addresses
- **`search_products`** - Searches available products by query at a specific delivery address
- **`get_cart`** - Fetches current cart state with items, pricing, and bill breakdown
- **`update_cart`** - Replaces entire cart with specified items
- **`checkout`** - Creates order and confirms payment (currently supports COD only)

## Getting Started

### Supported OAuth Redirect URIs

The following redirect URIs are whitelisted for MCP authentication:

- `claude://claude.ai/settings/connectors`
- `https://chatgpt.com/connector_platform_oauth_redirect`
- `https://claude.ai/api/mcp/auth_callback`
- `https://insiders.vscode.dev/redirect`
- `https://oauth.pstmn.io/v1/callback`
- `https://vscode.dev/redirect`
- `http://localhost`
- `http://localhost/callback`
- `http://127.0.0.1`
- `http://127.0.0.1/callback`

Contact the Swiggy team if you need additional URIs whitelisted.

### Setup Instructions

#### For Cursor Users

**Quick Install:** Copy and paste this link in your browser:

```
cursor://anysphere.cursor-deeplink/mcp/install?name=swiggy-instamart&config=eyJ0eXBlIjoiaHR0cCIsInVybCI6Imh0dHBzOi8vbWNwLnN3aWdneS5jb20vaW0ifQ==
```

**Manual Setup:** Update your `mcp.json` configuration file located in `~/.cursor/mcp.json` with:

```json
{
  "mcpServers": {
    "swiggy-instamart": {
      "type": "http",
      "url": "https://mcp.swiggy.com/im"
    },
    "swiggy-food": {
      "type": "http",
      "url": "https://mcp.swiggy.com/food"
    }
  }
}
```

Save the file and reload Cursor to activate the integration.

#### For Claude Desktop Users

1. Open Claude Desktop
2. Go to **Settings → Developer → Edit Config**
3. Add the following to `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "swiggy-instamart": {
      "type": "http",
      "url": "https://mcp.swiggy.com/im"
    },
    "swiggy-food": {
      "type": "http",
      "url": "https://mcp.swiggy.com/food"
    }
  }
}
```

4. Save and restart Claude Desktop

#### Other MCP Clients

Add this to your MCP manifest:

```json
{
  "mcpServers": {
    "swiggy-instamart": {
      "type": "http",
      "url": "https://mcp.swiggy.com/im"
    },
    "swiggy-food": {
      "type": "http",
      "url": "https://mcp.swiggy.com/food"
    }
  }
}
```

## Workflows You Can Try

### 🍔 Food Ordering Workflows

#### 🍕 Cuisine Discovery
> Craving something specific, explore options by cuisine

```
I'm craving some authentic South Indian food. Find me the best-rated restaurants 
nearby that serve dosas and filter coffee. Show me their top dishes.
```

#### 🌙 Late Night Cravings
> Finding restaurants open late

```
It's midnight and I'm hungry. What restaurants are still open near my home? 
I want something quick - maybe biryani or rolls. Show me options with delivery time under 30 mins.
```

#### 👥 Team Lunch Order
> Ordering food for the office team

```
I need to order lunch for 8 people at the office. We want a mix of:
- Vegetarian options (paneer dishes, dal)
- Non-veg (chicken biryani, kebabs)
- Some healthy salads
Budget is around ₹300 per person. Suggest a restaurant and build the order.
```

#### 🥗 Healthy Meal Finder
> Looking for nutritious options

```
I'm trying to eat healthy. Find me restaurants that serve:
- High protein meals
- Low calorie bowls
- Salads with grilled chicken
Show me options with calorie information if available. Deliver to home.
```

#### 💸 Budget Meals
> Delicious food without breaking the bank

```
I want a filling dinner under ₹150. Show me the best value meals nearby - 
could be a combo, thali, or biryani. Sort by ratings.
```

#### ⚡ Quick Lunch
> Fast delivery during work hours

```
I have a 30-minute lunch break. Find me restaurants with the fastest delivery 
that serve good North Indian or Chinese food. Order a quick combo meal to office.
```

---

### 🛒 Instamart Workflows

#### 🍛 Recipe-to-Cart
> Planning dinner, need all ingredients in one go.

```
I'm making Thai Green Curry tonight for 4 people. Can you search for the recipe, 
and let me know what items I need. Use my home address and add everything to cart.
```

#### 🥗 Dietary-Compliant Shopping
> Following specific diet (keto, vegan, diabetic, gluten-free)

```
I'm on a keto diet. Can you help me build a diet chart and the items I need for this. 
Make sure everything is low-carb and add to cart for my home address.
```

#### 📦 Weekly Meal Prep
> Sunday bulk cooking for the work week

```
I'm doing meal prep for 5 days. I need:
- 1kg chicken breast
- Bulk vegetables (broccoli, bell peppers, sweet potato)
- Quinoa and brown rice
- Olive oil and basic spices
Deliver to my home address.
```

#### 🎉 Party Shopping
> Hosting a weekend gathering

```
I'm hosting a party for 15 people. Help me shop for:
- Party snacks (chips, nachos, popcorn, nuts)
- Beverages (Coke, Sprite, juices)
- Frozen appetizers (paneer tikka, samosas)
- Ice cream and desserts
- Paper plates, cups, napkins
I need delivery to my home address.
```

#### 💰 Budget Shopping
> Student/tight budget, need to stay under limit

```
I have ₹500 budget for the week. Help me shop smart:
- Instant noodles (Maggi)
- Bread, jam, peanut butter
- Eggs (6-pack)
- Milk (500ml)
- Basic snacks
Show me the cart total and help me stay within budget. Home address.
```

#### 🏷️ Brand Comparison
> Price-conscious shopping, comparing options

```
I want to compare brands and prices for my monthly staples:
- Tea (Tata, Brooke Bond, Red Label)
- Cooking oil (Fortune, Sundrop)
- Milk (Amul, Mother Dairy, Nandini)
Show me options and help me pick the best value. Deliver to home.
```

## Tips for Best Results

- **Be Specific** - Mention quantities, brands if you have preferences
- **Provide Address Early** - "Use my home address" or "deliver to office"
- **Check Cart** - Always ask AI to show cart before checkout

## Important Notes

⚠️ **Current Limitations** - Third-party app development is not permitted at this time due to ongoing security reviews and compliance requirements. Stay tuned for updates on expanded access.

⚠️ **Keep the App Closed** - Do not open the Swiggy app while using these MCP integrations. Using both simultaneously may cause session conflicts or order processing issues.

⚠️ **COD Orders** - Be careful as it can place orders on your behalf under COD. Orders placed cannot be cancelled, so always review your cart before checkout.

**Support** - For issues or integration questions, contact the Swiggy developer team.

