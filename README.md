# miniJSONPath

## Code and Usage

```javascript
// code (that's all):

var mjp = (p, o, n) => p.split(/\.|\[|\]/).filter((x) => !!x).reduce((a, c, i, l) => l.length-i <= n ? a : a[c], o);

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

var path = 'y[0][0].z';

var nestedValue = mjp(path, obj);

console.log(nestedValue); // 4

// You can set a third argument to get the nth parent from the path
var nestedValueFirstParent = mjp(path, obj, 1); // {z: 4}
var nestedValueSecondParent = mjp(path, obj, 2); // [{"z":4}]

```
