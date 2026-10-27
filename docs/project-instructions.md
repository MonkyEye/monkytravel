# MonkeyTravel: project instructions

## What we're building
MonkeyTravel is a personalized, AI-generated trip planner, web page first and possibly a smartphone app later. A visitor answers a short quiz about how they like to travel. The product then suggests destinations that fit them and generates a full itinerary for the one they pick. Claude generates the recommendations and plans. The itinerary is free; the product does not sell or book trips. Possible later income: affiliate links to partner sites (flights, hotels, tours), not selling trips ourselves. The product is in English only for now.

## Who it's for
Launch audience: independent travelers on a mid budget. These are solo travelers, couples and small friend groups who book their own flights and stays and want help deciding where to go and how to spend their days: wandering, nature, adrenaline, socializing, avoiding touristy areas.
Later, not now: families and groups who want a relaxing holiday at an all-inclusive resort or in an apartment. Keep the quiz and prompts structured so this path can be added without a rewrite.
The traveler type stays a quiz question. It is asked first and decides which follow-up questions come next.

## The product flow
1. Quiz. It starts with the trip type and who is traveling, then branches into questions specific to that type (see quiz principles), and always covers budget, trip length and travel month.
2. Three destination options, each with a "why this fits you" line and a short list of things to see or experience.
3. The user picks one, and a full day-by-day itinerary is generated, matched to their trip type: accommodation suggestions, restaurants, activities and transport as relevant. The user can edit it ("make day 3 calmer").

## About me
This is my first time building a software project. Explain technical choices in plain language, say what each step is for, and give exact, step-by-step instructions for anything I have to do myself (creating accounts, API keys, deployment). Don't assume I know developer jargon. Recommend one default option rather than listing many.

## How to work with me
- Be direct and honest. Tell me when an idea is weak, risky or more expensive than it looks.
- For anything non-trivial, propose the approach briefly first, then build once I agree.
- Build in stages: working prototype first, then add layers. Don't add features I haven't asked for.
- Keep prototype code simple and readable, with short comments explaining the important parts.

## Technical direction
- Web page first. Claude is called from a backend, never from the browser, so the API key stays secret.
- Use structured JSON between steps (destination cards, itinerary days) so the page can render them reliably.
- Planned later: a verification step in the backend that checks every suggested place (existence, closure status, opening hours) using Tripadvisor's content API and Amazon Location Service for geocoding and travel times. Tripadvisor hotel data is also relevant for suggesting accommodation. The prototype skips this, but design the code so it can be added without a rewrite.
- Before relying on any third-party API's pricing, terms or storage limits, check the current documentation rather than assuming.

## Recommendation and itinerary quality rules
- Treat the quiz answers as hard constraints: budget, trip length, travel month, group type. A great match in the wrong season or price range is a failure.
- Let the traveler's stated preferences drive the style. If they want to avoid touristy areas, favor local neighborhoods, lesser-known spots and local-style experiences over the famous top-10 list. If they want an easy, comfortable holiday, favor convenience, good facilities and reliable choices, and do not push them toward off-the-beaten-path options they didn't ask for.
- Match the itinerary to the trip type. Backpackers get social hostels or areas, flexible routes, low-cost transport and nature or adrenaline options as asked. Families and groups get accommodation that suits them (resort or apartment), kid- or group-friendly activities where relevant, restaurants near where they stay, and a relaxed pace.
- Match pacing to personality. A wandering traveler gets unscheduled time and walkable areas. An adrenaline seeker gets active experiences with enough recovery built in.
- Keep itineraries realistic: sensible travel times between stops, no more than the traveler would actually enjoy per day, meals and rest included, stops grouped by area.
- Never invent places. If unsure whether a venue exists, is open, or what it costs, say so or mark it "verify before you go". Don't state prices or opening hours as fact unless verified.
- Every destination suggestion includes an honest "why this fits you" tied to specific quiz answers, and mentions any real downside (cost, crowds, weather, travel time).

## Quiz design principles
- Ask about how someone travels, not just where they want to go: what a perfect day looks like, planning versus wandering, what annoyed them on past trips, what they'd never do again.
- Start with a few universal questions (trip type, who's going), then branch. A backpacker gets questions about socializing, nature, adrenaline and daily budget. A family or friends group gets questions about resort versus apartment, activity level, kids' ages, and food preferences.
- Keep the quiz short (about 6-10 questions per person) and make each question change the result.

- When I suggest a tool, setup or approach, first check whether there is a better or more standard way to reach my goal. If there is, say so directly and recommend it before working within my suggestion. Lead with the best option, not the one I named.
