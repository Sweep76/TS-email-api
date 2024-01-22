![React Email code-block cover](https://react.email/static/covers/code-block.png)

<div align="center"><strong>@react-email/code-block</strong></div>
<div align="center">Display code with a selected theme and regex highlighting using Prism.js.</div>
<br />
<div align="center">
<a href="https://react.email">Website</a> 
<span> · </span>
<a href="https://github.com/resend/react-email">GitHub</a> 
<span> · </span>
<a href="https://react.email/discord">Discord</a>
</div>

## Install

Install component from your command line.

#### With yarn

```sh
yarn add @react-email/code-block -E
```

#### With npm

```sh
npm install @react-email/code-block -E
```

## Getting Started

Add the component into your email component as follows.

```jsx
import { CodeBlock, dracula } from "@react-email/code-block";

const Email = () => {
  const code = `export default async (req, res) => {
  try {
    const html = await renderAsync(
      EmailTemplate({ firstName: 'John' })
    );
    return NextResponse.json({ html });
  } catch (error) {
    return NextResponse.json({ error });
  }
}`;

  return (
    <CodeBlock
      code={code}
      lineNumbers // add this so that there are line numbers beside each code line
      theme={dracula}
      language="javascript"
    />
  );
};
```

This should render a code-block with the desired theme.

## Theming

Themes for this component are basically a set of styles for each kind of token that can result from prismjs's tokenization. See [here](https://prismjs.com/tokens.html) for more information on the tokens available.

An example of a theme would be this:

```json
{
  "base": {
    "color": "#f8f8f2",
    "background": "#282a36",
    "textShadow": "0 1px rgba(0, 0, 0, 0.3)",
    "fontFamily": "Consolas, Monaco, 'Andale Mono', 'Ubuntu Mono', monospace",
    "textAlign": "left",
    "whiteSpace": "pre",
    "wordSpacing": "normal",
    "wordBreak": "normal",
    "wordWrap": "normal",
    "lineHeight": "1.5",
    "MozTabSize": "4",
    "OTabSize": "4",
    "tabSize": "4",
    "WebkitHyphens": "none",
    "MozHyphens": "none",
    "MsHyphens": "none",
    "hyphens": "none",
    "padding": "1em",
    "margin": ".5em 0",
    "overflow": "auto",
    "borderRadius": "0.3em"
  },
  "comment": {
    "color": "#6272a4"
  },
  "prolog": {
    "color": "#6272a4"
  },
  "doctype": {
    "color": "#6272a4"
  },
  "cdata": {
    "color": "#6272a4"
  },
  "punctuation": {
    "color": "#f8f8f2"
  },
  "property": {
    "color": "#ff79c6"
  }
  // ...
}
```

Each token type can have their own defined styles and for each one of there can be any styles that can be applied directly to `React` elements.
As you can see from the example `dracula` theme though, there is a defined property called `base` which is the styling for the `pre` element that wraps the HTML being rendered.

For you to not need to defined a theme without any basis, or to not define one that already has been defined, we have many default themes exported from `@react-email/code-block`.
These themes were generated by a bit of code that converts a CSS file for a prismjs theme into a object theme of these.
If you want to generate a theme from another existing prismjs theme you can do so by looking into [this](https://github.com/gabrielmfern/from-prismjs-to-react-email-code-block-theme).

## Support

This component was tested using the most popular email clients.

| <img src="https://react.email/static/icons/gmail.svg" width="48px" height="48px" alt="Gmail logo"> | <img src="https://react.email/static/icons/apple-mail.svg" width="48px" height="48px" alt="Apple Mail"> | <img src="https://react.email/static/icons/outlook.svg" width="48px" height="48px" alt="Outlook logo"> | <img src="https://react.email/static/icons/yahoo-mail.svg" width="48px" height="48px" alt="Yahoo! Mail logo"> | <img src="https://react.email/static/icons/hey.svg" width="48px" height="48px" alt="HEY logo"> | <img src="https://react.email/static/icons/superhuman.svg" width="48px" height="48px" alt="Superhuman logo"> |
| -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Gmail ✔                                                                                           | Apple Mail ✔                                                                                           | Outlook ✔                                                                                             | Yahoo! Mail ✔                                                                                                | HEY ✔                                                                                         | Superhuman ✔                                                                                                |

## License

MIT License