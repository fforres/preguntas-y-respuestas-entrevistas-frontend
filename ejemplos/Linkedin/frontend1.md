### Question 1

1. Given the following, would you be able to let me know what the outcome for the last 3 lines is?

  ```javascript
    var Foo = function( a ) {+
      var baz = function() {
        return a;
      };
      this.baz = function() {
        return a;
      };
    };

    Foo.prototype = {
      biz: function() {
        return a;
      }
    };

    var f = new Foo( 7 );
    f.bar(); // bar funcition is not defined
    f.baz(); // 7
    f.biz(); // a undefined
  ```

  ##### Answer

  ```javascript
  f.bar(); // bar funcition is not defined
  f.baz(); // 7
  f.biz(); // a undefined
  ```

2. Would you be able to modify the code so f.bar() returned 7?

  ##### Answer
  You just need to add `baz` as a function to the "this" in the the Foo constructor

  ```javascript
    var Foo = function( a ) {+
      this.bar = function() {
        return a;
      };
      this.baz = function() {
        return a;
      };
    };

    Foo.prototype = {
      biz: function() {
        return a;
      }
    };

    var f = new Foo( 7 );
    f.bar(); // bar funcition is not defined
    f.baz(); // 7
    f.biz(); // a undefined
  ```

3. Can tou modify the code so f.biz() also returned 7?

    ##### Answer
    You need to add `a` to the this on the `Foo` constructor.
    And reference it (`this.a`) on the biz function.

    ```javascript
      var Foo = function( a ) {
        this.a = a; // Add a reference to A
        this.bar = function() {
          return a;
        };
        this.baz = function() {
          return a;
        };
      };

      Foo.prototype = {
        biz: function() {
          return this.a;
        }
      };

      var f = new Foo( 7 );
      f.bar(); // bar funcition is not defined
      f.baz(); // 7
      f.biz(); // a undefined
    ```

3. Imagine for some reason weird reason (Aliens...probably), that we cannot assing the `a` variable to anything, so doing `this.a = a`, is not possible. Could you achieve the same thing that in the past question?

  ```javascript
    var Foo = function( a ) {+
      // this.a = a;
      this.bar = function() {
        return a;
      }
      this.baz = function() {
        return a;
      };
      this._biz = function() {
        return a;
      };
    };

    Foo.prototype = {
      biz: function() {
        return this._biz();
      }
    };

    var f = new Foo( 7 );
    f.bar(); // here bar funcition is not defined
    f.baz(); // 7
    f.biz(); // a undefined
  ```


### Question 2

Given the following Array of endorsements
```javascript
var endorsements = [
  { skill: 'css', user: 'Bill' },
  { skill: 'javascript', user: 'Chad' },
  { skill: 'javascript', user: 'Bill' },
  { skill: 'css', user: 'Sue' },
  { skill: 'javascript', user: 'Sue' },
  { skill: 'html', user: 'Sue' }
];
```

How could you sort into something like this:
```javascript
[
  { skill: 'css', users: [ 'Bill', 'Sue', 'Sue' ], count: 2 },
  { skill: 'javascript', users: [ 'Chad', 'Bill', 'Sue' ], count: 3 },
  { skill: 'html', users: [ 'Sue' ], count: 1 }
]
```

  ##### Answer
  ```javascript
  const sortEndorsedArrays = (endorsements) => {
    const ob = {};
    endorsements.forEach(el => {
      if(!ob[el.skill]) {
        ob[el.skill] = {
          skill: el.skill,
          users: [],
          count: 0,
        }
      }
      ob[el.skill].user.push(el.user);
      ob[el.skill].count += 1;
    })

    let modifiedArray = [];
    Object.keys(ob).forEach(el => {
      modifiedArray.push(ob[el])
    })
    return modifiedArray;
  }
  ```

  > If you remember that objects saved assigned to objects or arrays are just a reference to said object, There's a way of improving that code.
  > And saving us of a whole iteration :)

  ```javascript
  const sortEndorsedArrays = (endorsements) => {
    const ob = {};
    const modifiedArray = [];
    endorsements.forEach(el => {
      if(!ob[el.skill]) {
        /*It happen from here: ----> */
        const endorsementObject = {
          skill: el.skill,
          users: [],
          count: 0,
        }
        ob[el.skill] = endorsementObject;
        modifiedArray.push(endorsementObject);
        /*
        To here
        <-------
        */
      }
      ob[el.skill].user.push(el.user);
      ob[el.skill].count += 1;
    })
    return modifiedArray;
  }
  ```
  ##### Explanation
  We create the an `endorsementObject`, kind of the same as before, but we:
  1. Save it in the Object.
    > So we can have the accesst ime  and `key uniqueness` capabilities or benefits of before)
  2. At the same time, push it in an array
    > So we can have our final structure ready to go, saving us a whole iteration on the process.

  While it can use more memory, but less computing time, it is a tradeoff you have to consider (And explaint it to your recruiter).
 Sorting 5 elements, it's not the same as sorting 10M


  -----


#### Question 3
Can you replicate the markup for the following?
  ![](./user_line.png)

> What I'm concerned is one of the rows for a user, not as much as the header/body of the container.
> We just want the template for a single item, we can asume we'll iterate over an array and print many of them.

This are open questions, vague on purpose, so remember to ask questions to frame your problem.

As an example, you could ask for the following:

- Are there any actions ths markup must perform? Buttons, links, the "close button" for example?
The idea is for me to write only css + html? Or interaction with JS also?
Is it responsive?
Is there any limitations?

###### Tips
  - Remember your aria / Accesibility
    - Use "li" instead of "div" for each "item"
    - use buttons for the "actions"

```css
  .row {
    display: flex;
    justify-content: space-between;
    padding: 0.5em;
  }
  .image {
    width: 100px;
  }
  .rowBody {
    flex-grow:2;
    display: flex;
    flex-direction: column;
  }
  .close {
    align-self: flex-start;
    width: 40px;
  }
  .description .profileLink {
    text-decoration: none;
  }
  .rowBody .description .name {
    /* bold */
  }
```
```html
  <li class="row">
    <div class="image">
      <img />
    </div>
    <div class="rowBody">
      <div class="description">
        <a href="{url}" class="profileLink"><span class="name">Jack Smith</span></a>
        <span>kaskjlasjlas</span>
      </div>
      <button class="connectButton"> +Connect </button>
    </div>
    <button class="close">
      x
    </button>
  </li>
```
