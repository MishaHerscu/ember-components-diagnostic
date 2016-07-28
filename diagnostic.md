# Ember Components Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  Give an example of a visual hierarchy that could be modeled with components.

    ```md
    A viewport that shows a collection of places I want to travel could be one.
    The overall list area is a component. Maybe each destination is a component
    that looks like a tile. And within each of those tiles I could have other components
    e.g. a to-do list for when I travel there.
    ```

1.  What is the command to generate a new component called '`my-map`'?

    ```sh
    ember generate component my-map
    ```

1.  What files are edited to produce a component, and what are their
    responsibilities?

    ```md
    There are two files in the component. The component.js file extends the
    Ember.Component object with additional logic. Actions for the component are
    defined in that file. The other file is the markup file, template.hbs, which is
    handlebars.
    ```

1.  Suppose you have a component '`my-contact`', which is loaded from
    '`app/contacts/template.hbs`' when visiting the `/contacts` path. What is
    the syntax for loading this component inside that template?

    ```html
    {{my-contact}} would be to just load the component, but you probably are passing
    in some data, maybe the contact information for yourself or someone else,
    so you probably have something like this:

    {{my-contact contact=contact}}

    or, if you want a loop:

    {{#each contacts as |contact|}}
      {{my-contact contact=contact}}
    {{/each}}
    ```

    Each contact has multiple phone numbers. Suppose you also have '`my-phone`'
    nested under '`my-contact`'. What is the code you would write in
    '`app/components/my-contact/template.hbs`' to load the nested component and
    pass it data?

    ```html
    {{#each numbers as |number|}}
      {{my-phone number=number}}
    {{/each}}
    ```
