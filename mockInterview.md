✅ Frontend Engineer with Next.js & Material UI – Mock Interview Q&A
🧠 Core Frontend (Next.js, React, MUI)
Q1. Walk me through your experience with Next.js. Which features have you actively used?
I've worked with SSR, static generation (getStaticProps), dynamic routing, API routes, and middleware. I've also used next/image for optimization and next/head for SEO.

Q2. How does SSR in Next.js differ from CSR in React?
SSR pre-renders the HTML on the server for each request. CSR renders on the client after JS loads. SSR improves initial load performance and SEO.

Q3. How do you handle global layouts in Next.js?
I define a Layout component and wrap pages using the custom getLayout pattern or by including it in \_app.tsx.

Q4. Tell me about a challenging component you built using MUI.
I built a custom MUI DataGrid with server-side pagination, row expansion, and dynamic filters. Styled using sx prop and styled() for theme overrides.

Q5. How do you handle responsiveness and accessibility with MUI?
I use MUI’s grid system and breakpoints for responsiveness. For accessibility, I rely on aria attributes, keyboard navigation support, and follow WCAG guidelines.

🧩 TypeScript & JavaScript (ES6+)
Q6. How do you decide when to use interface vs type?
Use interface for object shapes, especially when extending. Use type for unions, mapped types, or when combining multiple types.

Q7. Explain keyof and mapped types.
keyof gets a union of keys from a type. Mapped types loop over keys to build new types. Useful for utilities like Partial<T> or Readonly<T>.

Q8. Bug TypeScript helped you catch early?
Type mismatch between API response and UI assumption—TS flagged missing fields in a response object that would have caused runtime errors.

Q9. Fetch data using async/await:

ts
Copy
Edit
try {
const res = await fetch('/api/products');
if (!res.ok) throw new Error('Failed');
const data = await res.json();
} catch (err) {
console.error(err);
}
Q10. Difference between == and ===?
== allows type coercion ('1' == 1 is true). === checks both type and value. Always prefer === for safety.

🧪 Testing (Cypress / Playwright)
Q11. Frameworks used and preference?
Used Cypress and Playwright. Prefer Cypress for UI flow, Playwright for speed and parallel runs in CI.

Q12. Cypress test for login form:

js
Copy
Edit
cy.get('input[name=email]').type('user@example.com');
cy.get('input[name=password]').type('password');
cy.get('button[type=submit]').click();
cy.contains('Welcome');
Q13. How do you mock API calls in e2e tests?
In Cypress: cy.intercept() for mocking. In Playwright: use page.route() to mock responses.

Q14. Strategies to avoid flaky tests?
Avoid setTimeout, use cy.get().should(), control network with mocks, ensure deterministic test data.

Q15. How do you test accessibility interactions?
Use keyboard events (Tab, Enter), cy.realPress() for key handling, and run axe-core accessibility scans.

🔧 Node.js / Express.js
Q16. Built an endpoint in Express?
Yes, e.g., POST /api/login, which validates credentials, generates JWT, and returns it.

Q17. Middleware structure?
I split middlewares: auth, logging, error handling. Use app.use() for globals, and per-route for custom logic.

Q18. Input validation in Express?
I use express-validator or Joi to validate and sanitize request body/query/params.

Q19. Handling error responses on frontend?
I show contextual error messages with try/catch, check res.status, and display feedback via toasts or inline UI.

Q20. SSR with custom Express server in Next.js?
Yes, used custom server to handle auth, redirects, and internationalization before rendering via app.render().

💬 Conversational AI / NLP (Bonus)
Q21. Worked with Dialogflow/Lex?
Integrated Dialogflow with React chatbot widget—used fulfillment for dynamic responses.

Q22. Embedding chatbot in React UI—considerations?
Accessibility (ARIA roles), tab order, mobile responsiveness, session management, and async loading to avoid main thread blocking.

Q23. Familiar with intent/entity/context?
Yes. Intent = user goal, entity = data points (e.g., date), context = dialogue state. Crucial for natural flow.

Q24. Logging user interactions?
Track events using an analytics layer (e.g., Segment), log messages, intents, and responses with timestamps in DB.

Q25. Explored Rasa or NLU.js?
Yes—Rasa for on-prem NLP control, NLU.js for simple browser-based tasks. Rasa’s training pipeline is powerful and customizable.
