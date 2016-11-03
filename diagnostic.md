# Ember Components Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  Give an example of a visual hierarchy that could be modeled with components. Explain why each piece might be it's own component.

    ```md
    I'm not sure if I understand the question correctly, but:

    If you wanted an item to persist on each page, like a nav bar, you
    could put the code for that in your `applications` folder.
    Any view-state (not 'page'!) that you wanted to be a child of
    the root view-state, which we be what renders on the intial page-load, you could nest as a component. Components can have siblings, and can also have children themselves. In the URL, each component child view-state would be respresented like so:
      www.mycoolapp.com/<nested-component-name>
    ```

1.  What is the command to generate a new component called '`my-map`'?

    ```sh
    ember g component my-map (g as shorthand for generate)
    ```

1.  What files are created and/or edited to produce a component, and what are their responsibilities?

    ```md
    Template files, with the file extension .hbs (for handlebars) are
    responsible for binding data and registering actions.

    Component files (component.js) are where you define the actions and declare your html attributes.

    In general, we follow the "data down, actions up" convention in Ember, so that data is passed down through your file structure, and actions are passed up.

    ```

1.  Suppose you have a component '`my-contact`', which is loaded from
    '`app/contacts/template.hbs`' when visiting the `/contacts` route. What is
    the syntax (code that is written) to render this component inside that template?

    ```html
    {{#each model as |contact|}}
      {{my-contact contact=contact}}
    {{/each}}
    ```

1.  Each contact has multiple phone numbers. Suppose you also have '`my-phone`'
    nested under '`my-contact`'. What is the code you would write in
    '`app/components/my-contact/template.hbs`' to load the nested component and
    pass it data?

    ```html
    {{#each contact.phones as |phone|}}
      {{my-phone phone=phone}}
    {{/each}}
    ```
