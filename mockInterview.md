# ✅ Frontend Engineer with Next.js & Material UI – Mock Interview Q&A

## 🧠 Core Frontend (Next.js, React, MUI)

**Q1. Walk me through your experience with Next.js. Which features have you actively used?**  
I've worked with SSR, static generation (`getStaticProps`), dynamic routing, API routes, and middleware. I've also used `next/image` for optimization and `next/head` for SEO.

**Q2. How does SSR in Next.js differ from CSR in React?**  
SSR pre-renders the HTML on the server for each request. CSR renders on the client after JS loads. SSR improves initial load performance and SEO.

**Q3. How do you handle global layouts in Next.js?**  
I define a `Layout` component and wrap pages using the custom `getLayout` pattern or by including it in `_app.tsx`.

**Q4. Tell me about a challenging component you built using MUI.**  
I built a custom MUI `DataGrid` with server-side pagination, row expansion, and dynamic filters. Styled using `sx` prop and `styled()` for theme overrides.

**Q5. How do you handle responsiveness and accessibility with MUI?**  
I use MUI’s grid system and breakpoints for responsiveness. For accessibility, I rely on `aria` attributes, keyboard navigation support, and follow WCAG guidelines.

---

## 🧩 TypeScript & JavaScript (ES6+)

**Q6. How do you decide when to use `interface` vs `type`?**  
Use `interface` for object shapes, especially when extending. Use `type` for unions, mapped types, or when combining multiple types.

**Q7. Explain `keyof` and mapped types.**  
`keyof` gets a union of keys from a type. Mapped types loop over keys to build new types. Useful for utilities like `Partial<T>` or `Readonly<T>`.

**Q8. Bug TypeScript helped you catch early?**  
Type mismatch between API response and UI assumption—TS flagged missing fields in a response object that would have caused runtime errors.

**Q9. Fetch data using async/await:**

```ts
try {
  const res = await fetch("/api/products");
  if (!res.ok) throw new Error("Failed");
  const data = await res.json();
} catch (err) {
  console.error(err);
}
```

## ✅ Frontend Engineer with Next.js & Material UI – Mock Interview Q&A (Q10–Q25)

---

## 🧩 TypeScript & JavaScript (continued)

**Q10. Difference between `==` and `===`?**  
`==` allows type coercion (`'1' == 1` is true).  
`===` checks both type and value.  
Always prefer `===` for stricter, safer comparisons.

---

## 🧪 Testing (Cypress / Playwright)

**Q11. Frameworks used and preference?**  
Used both Cypress and Playwright.  
Prefer Cypress for rich UI flow testing, Playwright for performance, headless mode, and better CI integration.

**Q12. Cypress test for login form:**

```js
cy.get("input[name=email]").type("user@example.com");
cy.get("input[name=password]").type("password");
cy.get("button[type=submit]").click();
cy.contains("Welcome");
```

### 🧪 Testing (Cypress / Playwright)

**Q13. How do you mock API calls in e2e tests?**

- **Cypress:** Use `cy.intercept()` to mock/fake API responses.
- **Playwright:** Use `page.route()` to intercept requests and provide custom responses.

**Q14. Strategies to avoid flaky tests?**

- Avoid arbitrary waits (`setTimeout`).
- Use retryable assertions (`cy.get(...).should(...)`).
- Mock unstable network requests.
- Keep test data deterministic and reset state before each test.

**Q15. How do you test accessibility interactions?**

- Simulate keyboard navigation (`Tab`, `Enter`, `Arrow keys`).
- Use tools like `axe-core` for automated accessibility checks.
- Validate ARIA roles and keyboard behavior with Cypress plugins or Playwright selectors.

---

### 🔧 Node.js / Express.js

**Q16. Built an endpoint in Express?**  
Yes, for example, a `POST /api/login` endpoint:

- Validates user credentials.
- Issues JWT on success.
- Returns error messages for failed auth.

**Q17. Middleware structure?**

- `app.use()` for global middlewares like logging, error handling.
- Route-level middleware for auth checks or request-specific validation.

**Q18. Input validation in Express?**

- Use `express-validator` or `Joi`.
- Validate body, query, and params.
- Sanitize inputs to prevent XSS/SQL injection.

**Q19. Handling error responses on frontend?**

- Wrap API calls in `try/catch`.
- Inspect status codes and message payload.
- Show toast notifications or inline form errors.

**Q20. SSR with custom Express server in Next.js?**  
Yes. Used custom Express server to:

- Add middleware (auth, localization).
- Handle redirects and custom routes.
- Call `app.render()` to hand control back to Next.js.

---

### 💬 Conversational AI / NLP (Bonus)

**Q21. Worked with Dialogflow/Lex?**  
Yes. Integrated Dialogflow chatbot in React UI.

- Used webhook fulfillment.
- Passed context back to backend services.

**Q22. Embedding chatbot in React UI — considerations?**

- Accessibility: Ensure ARIA labels and keyboard navigation.
- Responsive: Fit in mobile and desktop views.
- Performance: Lazy-load bot scripts.
- Maintain session and state for continuity.

**Q23. Familiar with intent/entity/context?**  
Yes:

- **Intent:** What user wants (e.g., "book flight").
- **Entity:** Data needed (e.g., date, destination).
- **Context:** Track flow (e.g., asking follow-up questions).

**Q24. Logging user interactions?**

- Capture each message with timestamp and user/session ID.
- Store in analytics tools or custom backend (e.g., MongoDB, Segment).
- Include intents, entities, and bot responses for analysis.

**Q25. Explored Rasa or NLU.js?**  
Yes:

- Rasa offers full control, works well on-premises.
- NLU.js is lightweight, browser-friendly.
- Rasa’s pipelines are more robust for multilingual/chat history handling.
