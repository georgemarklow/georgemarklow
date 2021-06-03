# Jasmine

## Cheatsheet

Source: https://devhints.io/jasmine

<br/>

### Writing tests

```javascript
describe('A suite', () => {
  it('works', () => {
    expect(true).toBe(true)
  })
})
```

<br/>

### Hooks

```javascript
beforeEach(() => {
  ···
})
afterEach(() => {
  ···
})
```

<br/>

### Expectations

```javascript
expect(true).toBe(true)
expect(true).not.toBe(true)
```
```javascript
expect(a).toEqual(bar)
```
```javascript
expect(message).toMatch(/bar/)
expect(message).toMatch('bar')
```
```javascript
expect(a.foo).toBeDefined()
expect(a.foo).toBeUndefined()
expect(a.foo).toBeNull()
```
```javascript
expect(a.foo).toBeTruthy()
expect(a.foo).toBeFalsy()
```
```javascript
expect(message).toContain('hello')
```
```javascript
expect(pi).toBeGreaterThan(3)
expect(pi).toBeLessThan(4)
expect(pi).toBeCloseTo(3.1415, 0.1)
```
```javascript
expect(func).toThrow()
```

<br/>

### Spies 

```javascript
spyOn(foo, 'setBar')
spyOn(foo, 'setBar').andReturn(123)
spyOn(foo, 'getBar').andCallFake(function() { return 1001; })
foo.setBar(123)
```
```javascript
expect(foo.setBar).toHaveBeenCalled()
expect(foo.setBar).toHaveBeenCalledWith(123)
expect(foo.setBar.calls.length).toEqual(2)
expect(foo.setBar.calls[0].args[0]).toEqual(123)
```

<br/>

### Spies 
```javascript
test('works with promises', () => {
  return new Promise((resolve, reject) => {
    ···
  })
})
```
###

<br/>

### Pending 

```javascript
xit('this is a pending test', () => {
  ···
})
xdescribe('this is a pending block', () => {
  ···
})
```

<br/>

### Creating spies 

```javascript
stub = jasmine.createSpy('stub')
stub('hello')
expect(stub.identity).toEqual('stub')
expect(stub).toHaveBeenCalled()
```
