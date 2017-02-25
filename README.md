# react-nps-input

[![Build Status](https://travis-ci.org/GitbookIO/react-nps-input.svg?branch=master)](https://travis-ci.org/GitbookIO/react-nps-input)

A lightweight React component for gathering Net Promoter Score surveys. [See demo](http://samypesse.github.io/react-nps-input/).

### Installation

```
$ npm install react-nps-input --save
```

### Usage

```js
const React = require('react');
const NPSInput = require('react-nps-input');

const MyApp = React.createClass({
    onSubmit({ score }) {
        console.log(`Score for current user is ${score}/10`);
    },

    render() {
        return (
            <div>
                <NPSInput onSubmit={this.onSubmit}>{({ score }) => {
                    if (score >= 9) {
                        return <p>Awesome thank you!</p>;
                    } else {
                        return <p>Oh :(</p>;
                    }
                }}</NPSInput>
            </div>
        );
    }
})
```

### Props

- `[String] service` (Optional): name of the service for the introduction message
- `[Function] onSubmit`: function to call when the user clicked on a score
- `[Function] onDismissed`: function to call when the user clicked to dismiss the form
