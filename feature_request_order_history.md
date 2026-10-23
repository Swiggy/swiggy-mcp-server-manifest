# Feature Request: Order History Tool for Swiggy MCP Server

## Summary

**Request**: Expose an `order_history` tool in the Swiggy MCP Server to enable AI assistants to access users' past order data for building memory and personalized recommendation capabilities.

---

## Problem Statement

Currently, the Swiggy MCP Server exposes tools for:
- Restaurant/Product search
- Menu browsing
- Cart management
- Order placement

However, there is **no tool to retrieve a user's order history**. This limits the AI assistant's ability to provide truly personalized, context-aware recommendations.

### Use Case Example

> *"I'm hungry, what should I order?"*

Without order history, the AI can only provide generic suggestions. **With order history**, it could respond:

> *"Based on your history, you order burgers from McDonald's frequently (12 times in the last 3 months). Would you like your usual McSpicy Paneer Meal? You also seem to enjoy biryani on weekends - there's a Paradise Biryani nearby with great ratings."*

---

## Proposed Tool Specification

### Tool: `get_order_history`

**Description**: Retrieve the authenticated user's past orders including items, restaurants, dates, and order totals.

**Parameters**:
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `limit` | integer | No | Number of orders to fetch (default: 10, max: 50) |
| `days` | integer | No | Fetch orders from last N days (default: 90) |
| `service` | string | No | Filter by service: `food`, `instamart`, `dineout` |
| `restaurant_id` | string | No | Filter by specific restaurant |

**Example Response**:
```json
{
  "orders": [
    {
      "order_id": "OD123456789",
      "date": "2026-01-25T19:30:00+05:30",
      "restaurant": {
        "id": "rest_abc123",
        "name": "McDonald's",
        "cuisine": ["Fast Food", "Burgers"]
      },
      "items": [
        {
          "name": "McSpicy Paneer Meal",
          "quantity": 1,
          "price": 299
        }
      ],
      "total": 349,
      "status": "delivered"
    }
  ],
  "summary": {
    "total_orders": 45,
    "favorite_cuisines": ["Burgers", "Biryani", "Chinese"],
    "most_ordered_restaurant": "McDonald's"
  }
}
```

---

## Value Proposition

### 1. **Personalized Recommendations**
AI can recommend based on:
- Frequently ordered items
- Favorite cuisines/restaurants
- Time-based patterns (lunch vs dinner preferences)
- Weekend vs weekday habits

### 2. **Quick Re-ordering**
- *"Order my usual from Domino's"*
- *"Get me what I had last Tuesday"*
- *"Reorder my last Instamart groceries"*

### 3. **Smart Suggestions**
- *"I'm hungry"* → Suggests based on history + time of day
- *"Something healthy today"* → Knows you usually order burgers, suggests healthier alternatives
- *"Hosting a party"* → References past party orders for quantity guidance

### 4. **Budget Awareness**
- *"My usual, but cheaper"* → Suggests similar items at lower prices
- Monthly spending insights

### 5. **Dietary Pattern Analysis**
- Track ordering habits over time
- Help users make healthier choices
- Identify patterns they might not notice

---

## Privacy & Security Considerations

1. **User Consent**: Order history should only be accessible after explicit OAuth consent
2. **Data Minimization**: Only expose necessary fields (no payment details, exact addresses)
3. **Rate Limiting**: Implement appropriate rate limits to prevent abuse
4. **Audit Logging**: Track access to order history for security

---

## Implementation Suggestions

### Phase 1: Basic History
- Last N orders with basic details
- Simple filters (date range, service type)

### Phase 2: Analytics
- Aggregated insights (favorites, patterns)
- Cuisine/restaurant preferences

### Phase 3: Smart Features
- "Similar to previous order" suggestions
- Seasonal patterns

---

## Conclusion

The `order_history` tool would significantly enhance the MCP integration by enabling AI assistants to:
- Build memory of user preferences
- Provide personalized, context-aware recommendations
- Enable quick re-ordering workflows
- Create a more natural, assistant-like experience

This aligns with the goal of making AI assistants truly helpful for food ordering - not just executing commands, but understanding user preferences over time.

---

**Submitted by**: Muntazir Ali  
**Date**: 2026-01-30  
**Contact**: muntazirali2018@gmail.com
**GitHub**: https://github.com/iammuntazirali  
**MCP**: swiggy-food

---

*Thank you for considering this feature request. Happy to discuss implementation details or provide additional use cases.*
