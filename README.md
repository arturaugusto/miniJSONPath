# miniJSONPath

## Code and Usage

```javascript
// code (that's all):
var mjp = (p, o) => p.split(/\.|\[|\]/).filter((x) => !!x).reduce((a, c) => a[c], o);

// usage:

var obj = {
  "x": 1,
  "y": [
    [
      {
        "z": 4
      }
    ],
    [
      {
        "z": 6
      }
    ]
  ]
};

var path = 'y[0][0].z'

var nestedValue = mjp('y[0][0].z', obj)

console.log(nestedValue) // 4

```
