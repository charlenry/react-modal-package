# react-modal-package

This react component renders a modal with a message centered inside it with a close button. The react modal can be customized.

## Install this package:

```shell
npm install react-modal-package
```

##  Import the Modal component

```jsx
import Modal from "react-modal-package";
```

## Usage

This react modal takes in seven props :

- `displayState` - The open or closed state of the modal. It can be manage with a local state like in the example below. The two values are <b>block</b> and <b>none</b>. The modal is Hidden by default.
- `handleClose` - The callback that handles the close button of the modal.
- `message` - The message to display in the modal
- `bgColor` - The background color of the modal (optional)
- `textColor` - The text color of the message (optional)
- `textSize` - The text size of the message (optional)
- `btnColor` - The basic color of the close button (optional)

You need also to put the CSS code below in a CSS file in your project and import this file where the modal component is placed.

```css
/* The Modal (background) */
.modal {
  display: none; /* Hidden by default */
  position: fixed; /* Stay in place */
  z-index: 1; /* Sit on top */
  left: 0;
  top: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
}
.modal .modal-message {
  font-size: 2rem;
  font-weight: 600;
  color: #12002b;
  text-align: center;
  margin-top: 5rem;
}
/* Modal Content */
.modal .modal-content {
  background-color: #fefefe;
  margin: auto;
  padding: 2rem;
  border: 0.1rem solid #888;
  width: 80%;
  height: 15rem;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
    
}
/* The Close Button */
.modal .modal-content .close-button {
  color: #aaaaaa;
  float: right;
  font-size: 2rem;
  font-weight: bold;
}
.modal .modal-content .close-button:hover, 
.modal .modal-content .close-button:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
}
```
You can further customize your modal with this css code, especially for media queries.

### Example

```jsx
import { useState } from "react";
import Modal from "react-modal-package";

function App() {
  const [modalDisplayState, setModalDisplayState] = useState("none");

  const handleOpenModal = () => {
    setModalDisplayState("block");
  };

  const handleCloseModal = () => {
    setModalDisplayState("none");
  };

  return (
    <div>
      <button onClick={handleOpenModal}>Open Modal</button>
      <Modal
        displayState={modalDisplayState}
        handleClose={handleCloseModal}
        message="You have successfully used this modal!"
        bgColor=""
        textColor=""
        textSize=""
        btnColor=""
      />
    </div>
  );
}

export default App;
```
