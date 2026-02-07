# Example Inputs for scrape_local_businesses

Use one of the following input formats to generate a prospect list:

---

## Example 1: Simple Search Criteria

```
Vertical: Plumbers
Location: Seattle, WA
Feature Gap: No online booking
Limit: 25 businesses
```

---

## Example 2: Multiple Feature Gaps

```
Vertical: Dental Practices
Location: Austin, TX
Feature Gaps:
- No online booking
- No patient portal
- No live chat
Limit: 50 businesses

Minimum Rating: 4.0
Minimum Reviews: 20
```

---

## Example 3: Pasted Google Search Results

```
Search: "plumbers near me" - Seattle, WA

Results:

1. ABC Plumbing & Drain
   4.8 stars (234 reviews)
   "Open 24 hours"
   (206) 555-1234
   www.abcplumbingseattle.com
   123 Main St, Seattle, WA 98101

2. Rapid Response Plumbing
   4.5 stars (89 reviews)
   (206) 555-5678
   No website listed
   456 Oak Ave, Seattle, WA 98102

3. Seattle Pro Plumbers
   4.9 stars (312 reviews)
   "Emergency service available"
   (206) 555-9012
   www.seattleproplumbers.com
   789 Pine St, Seattle, WA 98103

[continue with more results...]

Feature Gap to Check: Online booking capability
```

---

## Example 4: CSV/Spreadsheet Data

```
Business Data (CSV format):

name,phone,website,rating,reviews,address
"Mike's HVAC","512-555-1111","mikeshvac.com",4.7,156,"100 Congress Ave, Austin TX"
"CoolAir Systems","512-555-2222","",4.2,43,"200 Lamar Blvd, Austin TX"
"Austin Comfort Heating","512-555-3333","austincomfort.net",4.9,287,"300 South 1st, Austin TX"

Feature Gap: No online scheduling
Sort By: Review count (highest first)
```

---

## Example 5: Google Maps Data

```
Extracted from Google Maps: "HVAC contractors Dallas TX"

Premier Air Conditioning
⭐ 4.6 (178 reviews)
📍 1234 Commerce St, Dallas, TX 75201
📞 (214) 555-0001
🌐 premierairdallas.com
Hours: Mon-Fri 8am-6pm, Sat 9am-2pm
Services: AC repair, heating, installation

---

Lone Star Cooling
⭐ 4.3 (67 reviews)
📍 5678 Elm St, Dallas, TX 75202
📞 (214) 555-0002
🌐 No website
Hours: Mon-Fri 7am-5pm
Services: Residential AC

---

[more businesses...]

Analyze for: Missing chatbot or 24/7 booking option
```

---

## Example 6: Yelp/Directory Listing

```
Source: Yelp search for "landscaping" in Denver, CO

Green Thumb Landscaping
★★★★☆ 4.0 (45 reviews)
$ - Landscaping, Lawn Services
"Family owned since 1995"
(303) 555-1234
www.greenthumbdenver.com
Serves Denver metro area

---

Rocky Mountain Lawns
★★★★★ 5.0 (12 reviews)
$$ - Landscaping, Hardscaping
(303) 555-5678
No website
Serves: Denver, Aurora, Lakewood

---

Mile High Outdoor Living
★★★★☆ 4.5 (89 reviews)
$$$ - Landscaping, Outdoor Kitchens, Pools
(303) 555-9012
www.milehighoutdoor.com
"Award-winning designs"

Feature Gap: No quote request form or online estimates
Minimum Reviews: 25
```

---

## Example 7: Specific Niche + Criteria

```
Vertical: Med Spas / Aesthetic Clinics
Location: Miami, FL (within 25 miles)
Feature Gaps:
- No online booking for consultations
- No before/after gallery
- No virtual consultation option

Qualification Criteria:
- Minimum 4.0 stars
- Minimum 50 reviews
- Must have a website (no website = disqualify)
- Must offer Botox or fillers (our service niche)

Limit: 30 qualified prospects
Sort: By review count descending
```

---

## Example 8: Competitor Analysis Angle

```
Find businesses similar to: www.example-competitor.com
Location: Phoenix, AZ metro
Vertical: Same as competitor (pool service)

Look for businesses that:
- Have fewer reviews than competitor (< 100)
- Lower rating than competitor (< 4.5)
- Missing features competitor has:
  - Online booking
  - Chat widget
  - Service area map
  - Customer portal

Goal: Find businesses losing to competitor due to worse digital presence
```

---

## Quick Input Template

```
Vertical: [industry type]
Location: [city, state or region]
Feature Gap: [what digital feature are they missing?]
Limit: [number of results]

Optional Filters:
- Minimum Rating: [X.X]
- Minimum Reviews: [XX]
- Must Have Website: [Yes/No]
- Disqualify If: [criteria]

Data Source: [Search criteria only / Pasted results / CSV data]
```
