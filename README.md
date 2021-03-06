  # React NLP Annotate

Interface for doing various NLP tasks. [Here's a code playground](https://codesandbox.io/s/react-nlp-annotate-example-0jwms?file=/src/App.js). Please help this repository by adding documentation and issues!

- Audio transcription
- Text Labeling (Entity, Classification)
- Entity Relation Labeling

![screenshot 1](https://user-images.githubusercontent.com/1910070/91113515-c5987b00-e653-11ea-92b8-08fa60cf7619.png)

![screenshot 2](https://user-images.githubusercontent.com/1910070/76181462-8d7da880-6197-11ea-908f-96d988a7efc8.png)

![screenshot 3](https://user-images.githubusercontent.com/1910070/76181412-560efc00-6197-11ea-8eba-1f48768f5183.png)

## Installation

`npm install react-nlp-annotate`

## Usage

### Document Classification

```javascript
import NLPAnnotator from "react-nlp-annotate"

const MyComponent = () => (
  <NLPAnnotator
    type="label-document"
    labels={[
      {
        "id": "gryffindor",
        "displayName": "Gryffindor",
        "description": "Daring, strong nerve and chivalry."
      },
      {
        "id": "slytherin",
        "displayName": "Slytherin",
        "description": "Cunning and ambitious. Possibly dark wizard."
      }
    ]}
    multipleLabels={false}
    document="Harry"
    onChange={(classification) => {
      console.log("Harry is a " + classification)
    }}
  />
)
```

### Entity Relation Labeling

```javascript
import React from "react";
import NLPAnnotator from "react-nlp-annotate";

const labels = [
  {
    id: "gryffindor",
    displayName: "Gryffindor",
    description: "Daring, strong nerve and chivalry."
  },
  {
    id: "slytherin",
    displayName: "Slytherin",
    description: "Cunning and ambitious. Possibly dark wizard."
  }
];

export default () => (
    <NLPAnnotator
      hotkeysEnabled
      type="label-relationships"
      labels={labels}
      multipleLabels={false}
      document="Harry was an honest to god good man"
      onChange={(output) => {
        console.log("Output is...", output);
      }}
      // this is just for label-relationships
      entityLabels={labels}
      relationshipLabels={labels}
    />
  </div>
);
```
