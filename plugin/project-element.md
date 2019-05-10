---
description: >-
  Rather than physical files and folders, Rekit thinks a project consists of
  different type of meaningful project elements.
---

# Project Element

## Introduction

A project element is a virtual element which could consist of a set of files, a folder or even a single file.

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

