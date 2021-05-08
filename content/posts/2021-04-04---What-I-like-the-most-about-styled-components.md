---
title: What I like the most about styled-components
date: "2021-04-04T21:00:00.000Z"
template: "post"
draft: false
slug: "what-i-like-the-most-about-styled-components"
category: "React"
tags:
  - "React"
  - "styled-components"
description: "When I started writing my first lines of React code, the first thing I did was setting up Sass and CSS modules but then I discovered styled-components."
socialImage: "/media/what-i-like-the-most-about-styled-components.jpg"
---

When I started writing my first lines of React code, the first thing I did was setting up _Sass_ and _CSS modules_ because I liked working with well-structured stylesheets. Variables to define themes, files divided into groups - header, body, footer, etc. I remember it was so great renaming files from _App.css_ to _App.module.scss_.

But like all the best things in this doomed world, there was an end. And the end of all that beauty happened when I discovered [styled-components](https://styled-components.com/). Something far more beautiful than _CSS modules_, believe me.

I state that I never used _PostCSS_ or _CSS in JS_ so maybe I lost great things on the way. But I have no regrets because probably I'd ended up on _styled-components_ anyway.

I won't list here all the advantages that _styled-components_ brings to the table but only what I think it's worth mentioning. For the rest, [check out the official documentation](https://styled-components.com/docs).

### Unique class names

You can have two or more components with the same name until they are in different files. See the example below in which I have two styled components _Container_ and I use them in different files. The clash won't happen because _styled-components_ will create a hash for each of them, something like `Appstyles__Container-qk6y7u-9` and `Profilestyles__Container-awrt4d-2`.

```jsx
// App.js
import React from 'react';

import { Container, Text } from './App.styles.js';

const App = () => {
  <Container>
    ...
    <Text>Hello, there!</Text>
  </Container>;
};

export default App;

// Profile.js
import React from 'react';

import { Container } from './Profile.styles.js';

const Profile = () => {
  <Container>...</Container>;
};

export default Profile;
```

### Passing _props_ to components

In the example below you can see how I can easily change the _background-color_ of the _Container_ depending on a variable defined in the JavaScript code. This is a very powerful feature.

```jsx
// App.js
import React from 'react';

import { Container } from './App.styles.js';

const App = () => {
  <Container isError={true}>
    ...
    <p>Hello, there!</p>
  </Container>;
};

export default App;

// App.styles.js
import styled, { css } from 'styled-components';

export const Container = styled.div`
  ${({ isError }) =>
    isError
      ? css`
          background-color: red;
        `
      : css`
          background-color: white;
        `}
`;
```

### Styling inheritance

You'll be able to create styled components which inherit the style from another component

```jsx
// App.styles.js
import styled from 'styled-components';

export const Text = styled.p`
  font-family: sans-serif;
  font-size: 16px;
`;

export const ErrorText = styled(Text)`
  color: red;
`;

export const SuccessText = styled(Text)`
  color: green;
`;
```

### Theming

_syled-components_ allows you to easily work with different themes in you application. It provides you with a _ThemeProvider_ ot be used as you can see below.

```jsx
// App.js
import React from 'react';
import { ThemeProvider } from 'styled-components';

const theme = {
  colors: {
    lightBlue: "#AFDBD2",
  },
  ...
}

const App = () => (
  <ThemeProvider theme={theme}>
    <Container>
      ...
    </Container>
  </ThemeProvider>
);

export default App;
```

```jsx
// App.styles.js
import React from 'react';
import styled from 'styled-components';

export const Container = styled.div`
  ...
  background-color: ${props => props.theme.colors.lightBlue};
`;
```

You can also create a _Theme.js_ component, as follows

```jsx
// Theme.js
import React from 'react';
import { ThemeProvider } from 'styled-components';

const theme = {
  colors: {
    lightBlue: "#AFDBD2",
  },
  ...
}

const Theme = ({ children }) => (
  <ThemeProvider theme={theme}>
    {children}
  </ThemeProvider>
);

export default Theme;
```

```jsx
// App.js
import React from 'react';
import Theme from './Theme';

const App = () => (
  <Theme>
    <Container>...</Container>
  </Theme>
);

export default App;
```

_App.styles.js_ doesn't change.

And it's not over!! You can also use `higher-order components` and `React hooks` to get the theme style.

```jsx
import React from 'react';
import { withTheme } from 'styled-components';

class App extends React.Component {
  ...
  render () {
    ... // this.props.theme is available here
  }
}

export default withTheme(App);
```

```jsx
import React, { useContext } from 'react';
import { ThemeContext } from 'styled-components';

const App = () => {
  const themeContext = useContext(ThemeContext);

  return (
    ...
  );
}

export default withTheme(App);
```

As I said, these are the things I personally found amazing about styled-components working with it everyday. I'm sure there are more that you may find interesting for your projects.

So.. what do you think? Worth taking a look?