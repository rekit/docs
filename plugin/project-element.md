---
description: >-
  Rather than physical files and folders, Rekit thinks a project consists of
  different type of meaningful project elements. That is project data.
---

# Provide Project Data

## Introduction

A project element is a virtual element which could consist of a set of files, a folder or even a single file.

## Provide Project Data

Rekit will find plugins with `app.getProjectData` extension point to feed the project data, all returned values from different plugins are merged into the final project data. For example, a plugin may have below structure:

```javascript
module.exports = {
  name: 'my-plugin',
  app: {
    getProjectData() {
      return {
        elements: ['root'],
        elementById: {
          root: { id: 'v:root', name: 'Root', type: 'root' }
        }
      };
    }
  }
};
```

We can see project data should at lease have `elements` and `elementById` properties.

* **elements** It is only used for the project explorer as root nodes.
* **elementById** This is used for mapping `id` to element object.

NOTE: you should ensure all ids in `elements` or any children of element can be found in `elementById` .

## Element Object Schema

Project element is the key concept for a Rekit project, it is used for:

1. Show an entry in project explorer
2. Show in overview diagram
3. How to show as a tab
4. How to show in main area
5. Quick Open

A sample element object is as below:

```javascript
const element = {
  id: 'id',
  name: 'Name',
  type: 'my-type',
  children: [],
  views: [],
  parts: [],
};
```

## Organize Multiple Files into an Element

## Element in Project Explorer

## Show Element in the Tabs Bar

Rekit usually shows an element in two level tabs structure.

![Two Level Tab Structure](../.gitbook/assets/image.png)

To define sub-tabs of an element, you need to provide `views` property to the element. For example, to show the structure like above picture, you can use code like below:

```javascript
const element = {
  id: 'v:src/Component1.js',
  name: 'Component1',
  vies: [
    { key: 'diagram', name: 'Diagram' },
    { key: 'code', name: 'Code', target: 'src/Component1.js', isDefault: true },
    { key: 'style', name: 'Style', target: 'src/Component1.css' },
    { key: 'test', name: 'Test', target: 'src/Component1.test.js' },
  ],
};
```

## Element in Quick Open

## 

