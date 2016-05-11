# react-responsive-modal
A simple responsive react modal.

[![Build Status](https://travis-ci.org/pradel/react-responsive-modal.svg?branch=master)](https://travis-ci.org/pradel/react-responsive-modal)

You can find a demo [here](http://pradel.github.io/react-responsive-modal/).
Or you can run examples
```
git clone https://github.com/pradel/react-responsive-modal
cd react-responsive-modal
npm install
npm run build:examples
open examples/index.html
```

## Installation

`npm install react-responsive-modal --save`

## Usage

```jsx
import React from 'react';
import ReactDOM from 'react-dom';
import Modal from 'react-responsive-modal';

export default class App extends React.Component {
  constructor(props) {
    super(props);
    this.onOpenModal = this.onOpenModal.bind(this);
    this.onCloseModal = this.onCloseModal.bind(this);
    this.state = {
      open: false,
    };
  }

  onOpenModal() {
    this.setState({ open: true });
  }

  onCloseModal() {
    this.setState({ open: false });
  }

  render() {
    const { open } = this.state;
    return (
      <div>
        <button onClick={this.onOpenModal}>Open modal</button>
        <Modal open={open} onClose={this.onCloseModal} little>
          <h2>Simple centered modal</h2>
        </Modal>
      </div>
    );
  }
}

ReactDOM.render(<App />, document.getElementById('app'));
```

## Props

`open`: (Bool) Control if the modal is open or not.

`closeOnEsc`: (Bool) default: true is the modal closable when user press esc key.

`closeOnOverlayClick`: (Bool) default: true is the modal closable when user click on overlay.

`onClose`: (function) Fired when the Modal is requested to be closed by a click on the overlay or when user press esc key.

`little`: (Bool) Is the dialog centered __When you don't have a lot of content__.

`children`: (Node) The content of the modal.

`overlayClassName`: (String) Classname for overlay div.

`modalClassName`: (String) Classname for modal content div.

`overlayStyle`: (Object) Inline style for overlay div.

`modalStyle`: (Object) Inline style for modal content div.
