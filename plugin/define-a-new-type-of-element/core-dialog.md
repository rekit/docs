---
description: Core dialog is used to adding new elements with a form.
---

# Core Dialog

## Show a Dialog

To show the dialog, use the action `core/redux/showDialog` :

```javascript
import * as actions from 'rs/features/core/redux/actions';
import store from '../../../common/store';

const showDialog = (...args) => store.dispatch(actions.showDialog(...args));
```

showDialog accepts below arguments:

```text
showDialog(formId, title, context)
```

| Argument | Type | Description |
| :--- | :--- | :--- |
| formId | string | Which form to show in the dialog |
| title | string | Title of the dialog |
| context | object | The context for the form to render fields and submit values. |

The context object usually has below fields:

| Property | Type | Description |
| :--- | :--- | :--- |
| action | string | The action to manage element |
| targetId | string | Which element is the action applied. |
| elementType | string | When create, the type of the element to create. |

Besides the context before, all values user input in the form are provided to Rekit core command.

Then you can use `showDialog` in your logic like `handleMenuClick`:

```javascript
menu.contextMenu.handleMenuClick(key) {
  switch (key) {
    case 'plugin-default-new-file':
      showDialog('core.element.add.file', 'New File', {
        action: 'add',
        targetId: null,
        elementType: 'file',
      });
      break;
    case 'plugin-default-new-folder':
      showDialog('core.element.add.folder', 'New Folder', {
        action: 'add',
        targetId: null,
        elementType: 'folder',
      });
      break;
    default:
      break;
  }
}
```

