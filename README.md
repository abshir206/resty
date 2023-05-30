# resty

### Lab 27

Extend your React Application so that your functional components are able to manage their own state variables using the useState() Hook. NOTE: It is not a requirement to make the actual API call. That can be mocked with “fake” data.

- Refactor any components using this.setState() to implement the useState() react API hook.
- Refactor the Form Component to implement user input from form elements, instead of hard coded string values.
Suggested Component Hierarchy and Application Architecture:

- index.js - Entry Point.
- <App /> - Container.

  - Holds application state: The Request (from the form) and the Response (from the API).
  - Hook that can update state.
  - Renders 2 Child Components.

- <Form />
  - Expects a function to be sent to it as a prop.
  - Renders a URL entry form.
  - A selection of REST methods to choose from (“get” should be the default).
    - The active selection should be displayed/styled differently than the others.
  - Renders a Textarea to allow the user to type in a JSON object for a POST or PUT request.
  - On submit:
    - Send the Form entries back to the <App /> using the method sent down in props.
    - Form will run the API request.
      - Toggle the “loading” status before and after the request.

- <Results />
  - Conditionally renders “Loading” or the data depending on the status of the request.
  - Expects the count, headers, results to be sent in as props.
  - Renders the count.
  - Renders the Result Headers as “pretty” JSON.
  - Renders the Result Body as “pretty” JSON.