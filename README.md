# react-modal-package

This react component renders a modal with a message centered inside it with a close button.

## Install this package:

```shell
npm install @charlenry/react-modal-package
```

##  Import the Modal component

```jsx
import Modal from "@charlenry/react-modal-package";
```

## Usage

This react modal takes in three props :

- `displayState` - The open or closed state of the modal. It can be manage with a local state like in the example below. The two values are <b>block</b> and <b>none</b>. The modal is Hidden by default.
- `handleClose` - The callback that handles the close button of the modal.
- `message` - The message to display in the modal

The modal can be style in the Modal.scss file of the module. So you need to install sass.

```shell
npm install sass
```
or
```shell
yarn add sass
```

### Example

```jsx
import { useState } from "react";
import Modal from "@charlenry/react-modal-package";

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
      />
    </div>
  );
}

export default App;
```
