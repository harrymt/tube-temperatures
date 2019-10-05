# How Hot is the London Tube

Map showing the temperature of each tube line across the year 🔥

### Run/Deploy

```
$ cd app
$ yarn dev
$ yarn deploy
```

Starting template with:

- React.js
- Next.js
- Typescript
- SCSS
- Google analytics
- SSL (via Zeit Now)
- CI
- CD
- Jest tests


TODO setup github workflow:
```
name: Test cross-platform

on: [push]

jobs:
  test:
    name: Test on node ${{ matrix.node_version }} and ${{ matrix.os }}
    runs-on: ${{ matrix.os }}
    strategy:
      matrix:
        node_version: [12.0]
        os: [ubuntu-latest]

    steps:
    - uses: actions/checkout@v1
    - name: Use Node.js ${{ matrix.node_version }}
      uses: actions/setup-node@v1
      with:
        version: ${{ matrix.node_version }}

    - name: npm install, build and test
      run: |
        npm install
        npm run build --if-present
        npm test
```

## How to use

```javascript
npm i -g now
npm i
npm run dev
```

### Data

TFL supplies the open dataset for the average monthly temperatures for all lines (2013-2018)
https://data.london.gov.uk/dataset/london-underground-average-monthly-temperatures

### Pipeline

![Pipeline](./tube-temperatures-pipeline.png)
