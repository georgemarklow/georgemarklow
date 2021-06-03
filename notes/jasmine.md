# Jasmine

## Cheatsheet

Source: https://devhints.io/jasmine

### Writing tests

```javascript
describe('A suite', () => {
  it('works', () => {
    expect(true).toBe(true)
  })
})
```

### Hooks

```javascript
beforeEach(() => {
  ···
})
afterEach(() => {
  ···
})
```
