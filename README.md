# bigint-bitfield

```javascript
let compress = (arr) => arr.reduceRight((a, c, i) => a | (c ? (1n << BigInt(i)) : 0n), 0n)
let decompress = (n) => new Array((n).toString(2).length).fill(0).map((x, i) => BigInt(n) & 1n << BigInt(i) ? 1 : 0)

console.log(compress([1,0,1,1]) === 13n) // true
console.log([1,0,1,1].map((x, i) => x === decompress(13)[i])) // [true, true, true, true]
```
