# Swiggy MCP Server


Order food, groceries and more through intelligent MCP server integrations.

## Supported Features

### Swiggy Food

Food you 🧡, on time

**Restaurant Search** - Discover restaurants by cuisine, name, or dish

**Menu Browsing** - Explore menus, prices, and item details

**Cart Management** - Add items, customize orders, and view bill breakdown

**Food Ordering** - Place orders seamlessly with order tracking support (currently supports COD only)

---

### Instamart

Get groceries & more, delivered in mins!

**Product Search** - Find products by name, category, or brand at your delivery location

**Cart Management** - View cart items, pricing, and bill breakdown with detailed cost analysis

**Order Placement** - Seamlessly checkout and place grocery orders with instant confirmation (currently supports COD only)

---

### Dineout

Reserve tables at your favorite restaurants instantly.

**Restaurant Discovery** - Find nearby restaurants based on your location and preferences

**Restaurant Details** - Browse through detailed menus with prices, ratings, and exclusive offers

**Slot Availability** - Check available booking time slots for your preferred date

**Table Booking** - Reserve tables instantly with seamless booking support (supports free bookings only)

## Getting Started

### Supported OAuth Redirect URIs

PS: avoid ChatGPT right now since there are some issues with tool calls and it being a bit buggy with mcp's. More details - https://community.openai.com/t/issues-with-unstable-natural-language-invocation-and-duplicate-tool-calls/1370573/11

The following redirect URIs are whitelisted for MCP authentication:

- `claude://claude.ai/settings/connectors`
- `https://claude.ai/api/mcp/auth_callback`
- `https://insiders.vscode.dev/redirect`
- `https://oauth.pstmn.io/v1/callback`
- `https://vscode.dev/redirect`
- `http://localhost`
- `http://localhost/callback`
- `http://127.0.0.1`
- `http://127.0.0.1/callback`

Contact us if you need additional URIs whitelisted.

## Setup Instructions

### Add Swiggy MCPs to Cursor

### Food
[![Install MCP Server](https://cursor.com/deeplink/mcp-install-dark.svg)](
https://cursor.com/en-US/install-mcp?name=swiggy-food&config=eyJ0eXBlIjoiaHR0cCIsInVybCI6Imh0dHBzOi8vbWNwLnN3aWdneS5jb20vZm9vZCJ9
)

### Dineout
[![Install MCP Server](https://cursor.com/deeplink/mcp-install-dark.svg)](
https://cursor.com/en-US/install-mcp?name=swiggy-dineout&config=eyJ0eXBlIjoiaHR0cCIsInVybCI6Imh0dHBzOi8vbWNwLnN3aWdneS5jb20vZGluZW91dCJ9
)

### Instamart
[![Install MCP Server](https://cursor.com/deeplink/mcp-install-dark.svg)](
https://cursor.com/en-US/install-mcp?name=swiggy-instamart&config=eyJ0eXBlIjoiaHR0cCIsInVybCI6Imh0dHBzOi8vbWNwLnN3aWdneS5jb20vaW0ifQ%3D%3D
)

### Add Swiggy MCP Servers to VS Code

### Food
[![Install MCP Server](https://img.shields.io/badge/Install-MCP-blue)](
https://insiders.vscode.dev/redirect?url=vscode:mcp/install?%7B%22type%22%3A%22http%22%2C%22name%22%3A%22swiggy-food%22%2C%22version%22%3A%220.0.1%22%2C%22description%22%3A%22MCP%20server%20to%20interact%20with%20Swiggy%20Food%20services%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.swiggy.com%2Ffood%22%2C%22author%22%3A%22Swiggy%22%2C%22tags%22%3A%5B%22swiggy%22%2C%22food%22%2C%22mcp%22%5D%2C%22categories%22%3A%5B%22mcp%22%5D%7D
)

### Dineout
[![Install MCP Server](https://img.shields.io/badge/Install-MCP-blue)](
https://insiders.vscode.dev/redirect?url=vscode:mcp/install?%7B%22type%22%3A%22http%22%2C%22name%22%3A%22swiggy-dineout%22%2C%22version%22%3A%220.0.1%22%2C%22description%22%3A%22MCP%20server%20to%20interact%20with%20Swiggy%20Dineout%20services%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.swiggy.com%2Fdineout%22%2C%22author%22%3A%22Swiggy%22%2C%22tags%22%3A%5B%22swiggy%22%2C%22dineout%22%2C%22mcp%22%5D%2C%22categories%22%3A%5B%22mcp%22%5D%7D
)

### Instamart
[![Install MCP Server](https://img.shields.io/badge/Install-MCP-blue)](
https://insiders.vscode.dev/redirect?url=vscode:mcp/install?%7B%22type%22%3A%22http%22%2C%22name%22%3A%22swiggy-instamart%22%2C%22version%22%3A%220.0.1%22%2C%22description%22%3A%22MCP%20server%20to%20interact%20with%20Swiggy%20Instamart%20services%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.swiggy.com%2Fim%22%2C%22author%22%3A%22Swiggy%22%2C%22tags%22%3A%5B%22swiggy%22%2C%22instamart%22%2C%22mcp%22%5D%2C%22categories%22%3A%5B%22mcp%22%5D%7D
)

### OR

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
    },
    "swiggy-dineout": {
      "type": "http",
      "url": "https://mcp.swiggy.com/dineout"
    }
  }
}
```

Save the file and reload Cursor to activate the integration.

#### For Claude Pro Desktop Users

1. Open Claude Desktop
2. Go to **Settings → Connectors → Add custom connector**
3. Add any Name
4. Add the URL:
   - Food: `https://mcp.swiggy.com/food`
   - Instamart: `https://mcp.swiggy.com/im`
   - Dineout: `https://mcp.swiggy.com/dineout`
5. Save and Restart Claude

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
    },
    "swiggy-dineout": {
      "type": "http",
      "url": "https://mcp.swiggy.com/dineout"
    }
  }
}
```

## Workflows You Can Try

### Food Ordering Workflows

#### Cuisine Discovery
> Craving something specific, explore options by cuisine

```
I'm craving some authentic South Indian food. Find me the best-rated restaurants 
nearby that serve dosas and filter coffee. Show me their top dishes.
```

#### Late Night Cravings
> Finding restaurants open late

```
It's midnight and I'm hungry. What restaurants are still open near my home? 
I want something quick - maybe biryani or rolls. Show me options with delivery time under 30 mins.
```

#### Team Lunch Order
> Ordering food for the office team

```
I need to order lunch for 8 people at the office. We want a mix of:
- Vegetarian options (paneer dishes, dal)
- Non-veg (chicken biryani, kebabs)
- Some healthy salads
Budget is around ₹300 per person. Suggest a restaurant and build the order.
```

#### Healthy Meal Finder
> Looking for nutritious options

```
I'm trying to eat healthy. Find me restaurants that serve:
- High protein meals
- Low calorie bowls
- Salads with grilled chicken
Show me options with calorie information if available. Deliver to home.
```

#### Budget Meals
> Delicious food without breaking the bank

```
I want a filling dinner under ₹150. Show me the best value meals nearby - 
could be a combo, thali, or biryani. Sort by ratings.
```

#### Bolt
> Fast delivery during work hours

```
I have a 30-minute lunch break. Find me restaurants with the fastest delivery 
that serve good North Indian or Chinese food. Order a quick combo meal to office.
```

---

### Instamart Workflows

#### Recipe-to-Cart
> Planning dinner, need all ingredients in one go.

```
I'm making Thai Green Curry tonight for 4 people. Can you search for the recipe, 
and let me know what items I need. Use my home address and add everything to cart.
```

#### Dietary-Compliant Shopping
> Following specific diet (keto, vegan, diabetic, gluten-free)

```
I'm on a keto diet. Can you help me build a diet chart and the items I need for this. 
Make sure everything is low-carb and add to cart for my home address.
```

#### Weekly Meal Prep
> Sunday bulk cooking for the work week

```
I'm doing meal prep for 5 days. I need:
- 1kg chicken breast
- Bulk vegetables (broccoli, bell peppers, sweet potato)
- Quinoa and brown rice
- Olive oil and basic spices
Deliver to my home address.
```

#### Party Shopping
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

#### Budget Shopping
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

#### Brand Comparison
> Price-conscious shopping, comparing options

```
I want to compare brands and prices for my monthly staples:
- Tea (Tata, Brooke Bond, Red Label)
- Cooking oil (Fortune, Sundrop)
- Milk (Amul, Mother Dairy, Nandini)
Show me options and help me pick the best value. Deliver to home.
```

---

### Dineout Workflows

#### Weekend Dinner Plans
> Finding and booking a table for date night

```
I want to take my partner out for dinner this Saturday evening around 8 PM. 
Find me good Italian restaurants in Koramangala with romantic ambiance. 
Check availability and book a table for 2 if there are slots.
```

#### Group Celebration
> Booking for friends or family gatherings

```
We're celebrating a birthday with 6 friends this Friday at 7:30 PM. 
Find restaurants in Indiranagar that serve North Indian food, have good ratings, 
and can accommodate a group. Check which ones have free booking slots and reserve a table.
```

#### Exploring New Restaurants
> Discovering dining options with offers

```
I'm looking to try new restaurants in Whitefield this week. Show me top-rated places 
with active dineout offers. I prefer continental or Asian cuisine. 
What are my options for dinner tomorrow at 8 PM?
```

## Tips for Best Results

**For Food & Instamart:**
- **Be Specific** - Mention quantities, brands, dietary preferences
- **Provide Address Early** - "Use my home address" or "deliver to office"
- **Check Cart** - Always review cart before checkout

**For Dineout:**
- **Specify Locality** - Mention area/neighborhood (e.g., "Koramangala", "Indiranagar")
- **State Party Size** - Number of people and date/time
- **Free Bookings Only** - Currently supports free reservations

## Important Notes

⚠️ **Current Limitations** - Third-party app development is not permitted at this time due to ongoing security reviews and compliance requirements. Stay tuned for updates on expanded access.

⚠️ **Keep the App Closed** - Do not open the Swiggy app while using these MCP integrations. Using both simultaneously may cause session conflicts or order processing issues.

⚠️ **COD Orders** - Be careful as it can place orders on your behalf under COD. Orders placed cannot be cancelled, so always review your cart before checkout.

**Support** - For issues or integration questions, contact the Swiggy developer team.
