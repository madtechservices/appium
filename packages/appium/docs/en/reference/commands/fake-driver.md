# Driver: fake-driver

## Commands

### `callDeprecatedCommand`

`POST` **`/session/:sessionId/deprecated`**

This is a command that exists just to be an example of a deprecated command

<!-- comment source: method-signature -->

#### Response

``null``

### `doubleClick`

`POST` **`/session/:sessionId/doubleclick`**

Double-click the current mouse location

**`Deprecated`**

Use the Actions API instead

<!-- comment source: builtin-interface -->

#### Response

``null``

### `getFakeThing`

`GET` **`/session/:sessionId/fakedriver`**

#### Response

``null`` \| `Thing`

### `setFakeThing`

`POST` **`/session/:sessionId/fakedriver`**

Set the 'thing' value (so that it can be retrieved later)

<!-- comment source: method-signature -->

#### Parameters

| Name | Type |
| :------ | :------ |
| `thing` | `Thing` |

#### Response

``null``

### `getFakeDriverArgs`

`GET` **`/session/:sessionId/fakedriverargs`**

Get the driver args that were sent in via the CLI

<!-- comment source: method-signature -->

#### Response

`StringRecord` & `ServerArgs`

### `createSession`

`POST` **`/session`**

Comment for `createSession` in `FakeDriver`

**`See`**

[https://w3c.github.io/webdriver/#new-session](https://w3c.github.io/webdriver/#new-session)

<!-- comment source: multiple -->

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `desiredCapabilities?` | `W3CFakeDriverCaps` | W3C Capabilities |
| `requiredCapabilities?` | `W3CFakeDriverCaps` | W3C Capabilities |
| `capabilities?` | `W3CFakeDriverCaps` | W3C Capabilities |

#### Response

[`string`, `FakeDriverCaps`]

The capabilities object representing the created session

### `deleteSession`

`DELETE` **`/session/:sessionId`**

Returns capabilities for the session and event history (if applicable)

<!-- comment source: method-signature -->

#### Response

`SingularSessionData`<{ `app`: { `isString`: ``true`` = true; `presence`: ``true`` = true } ; `uniqueApp`: { `isBoolean`: ``true`` = true }  }, `StringRecord`\>

A session data object

### `getSession`

`GET` **`/session/:sessionId`**

Returns capabilities for the session and event history (if applicable)

<!-- comment source: multiple -->

#### Response

`SingularSessionData`<{ `app`: { `isString`: ``true`` = true; `presence`: ``true`` = true } ; `uniqueApp`: { `isBoolean`: ``true`` = true }  }, `StringRecord`\>

A session data object

### `findElement`

`POST` **`/session/:sessionId/element`**

Find a UI element given a locator strategy and a selector, erroring if it can't be found

**`See`**

[https://w3c.github.io/webdriver/#find-element](https://w3c.github.io/webdriver/#find-element)

<!-- comment source: method-signature -->

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `using` | `string` | the locator strategy |
| `value` | `string` | the selector to combine with the strategy to find the specific element |

#### Response

`Element`<`string`\>

The element object encoding the element id which can be used in element-related
commands

### `findElementFromElement`

`POST` **`/session/:sessionId/element/:elementId/element`**

Find a UI element given a locator strategy and a selector, erroring if it can't be found. Only
look for elements among the set of descendants of a given element

**`See`**

[https://w3c.github.io/webdriver/#find-element-from-element](https://w3c.github.io/webdriver/#find-element-from-element)

<!-- comment source: method-signature -->

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `using` | `string` | the locator strategy |
| `value` | `string` | the selector to combine with the strategy to find the specific element |

#### Response

`Element`<`string`\>

The element object encoding the element id which can be used in element-related
commands

### `findElementFromShadowRoot`

`POST` **`/session/:sessionId/shadow/:shadowId/element`**

Find an element from a shadow root

**`See`**

[https://w3c.github.io/webdriver/#find-element-from-shadow-root](https://w3c.github.io/webdriver/#find-element-from-shadow-root)

<!-- comment source: method-signature -->

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `using` | `string` | the locator strategy |
| `value` | `string` | the selector to combine with the strategy to find the specific elements |

#### Response

`Element`<`string`\>

The element inside the shadow root matching the selector

### `findElements`

`POST` **`/session/:sessionId/elements`**

Find a a list of all UI elements matching a given a locator strategy and a selector

**`See`**

[https://w3c.github.io/webdriver/#find-elements](https://w3c.github.io/webdriver/#find-elements)

<!-- comment source: method-signature -->

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `using` | `string` | the locator strategy |
| `value` | `string` | the selector to combine with the strategy to find the specific elements |

#### Response

`Element`<`string`\>[]

A possibly-empty list of element objects

### `findElementsFromElement`

`POST` **`/session/:sessionId/element/:elementId/elements`**

Find a a list of all UI elements matching a given a locator strategy and a selector. Only
look for elements among the set of descendants of a given element

**`See`**

[https://w3c.github.io/webdriver/#find-elements-from-element](https://w3c.github.io/webdriver/#find-elements-from-element)

<!-- comment source: method-signature -->

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `using` | `string` | the locator strategy |
| `value` | `string` | the selector to combine with the strategy to find the specific elements |

#### Response

`Element`<`string`\>[]

A possibly-empty list of element objects

### `findElementsFromShadowRoot`

`POST` **`/session/:sessionId/shadow/:shadowId/elements`**

Find elements from a shadow root

**`See`**

[https://w3c.github.io/webdriver/#find-element-from-shadow-root](https://w3c.github.io/webdriver/#find-element-from-shadow-root)

<!-- comment source: method-signature -->

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `using` | `string` | the locator strategy |
| `value` | `string` | the selector to combine with the strategy to find the specific elements |

#### Response

`Element`<`string`\>[]

A possibly empty list of elements inside the shadow root matching the selector

### `getLog`

`POST` **`/session/:sessionId/log`**

Get the log for a given log type.

<!-- comment source: method-signature -->

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | Name/key of log type as defined in ILogCommands.supportedLogTypes. |

#### Response

`any`

### `getLog`

`POST` **`/session/:sessionId/se/log`**

Get the log for a given log type.

<!-- comment source: method-signature -->

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type` | `string` | Name/key of log type as defined in ILogCommands.supportedLogTypes. |

#### Response

`any`

### `getLogEvents`

`POST` **`/session/:sessionId/appium/events`**

Get a list of events that have occurred in the current session

<!-- comment source: method-signature -->

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type?` | `string` \| `string`[] | filter the returned events by including one or more types |

#### Response

`EventHistory` \| `Record`<`string`, `number`\>

The event history for the session

### `getLogTypes`

`GET` **`/session/:sessionId/log/types`**

Get available log types as a list of strings

<!-- comment source: method-signature -->

#### Response

`string`[]

### `getLogTypes`

`GET` **`/session/:sessionId/se/log/types`**

Get available log types as a list of strings

<!-- comment source: method-signature -->

#### Response

`string`[]

### `getPageSource`

`GET` **`/session/:sessionId/source`**

Get the current page/app source as HTML/XML

**`See`**

[https://w3c.github.io/webdriver/#get-page-source](https://w3c.github.io/webdriver/#get-page-source)

<!-- comment source: method-signature -->

#### Response

`string`

The UI hierarchy in a platform-appropriate format (e.g., HTML for a web page)

### `getSessions`

`GET` **`/sessions`**

Get data for all sessions running on an Appium server

<!-- comment source: method-signature -->

#### Response

`MultiSessionData`<{ `app`: { `isString`: ``true`` = true; `presence`: ``true`` = true } ; `uniqueApp`: { `isBoolean`: ``true`` = true }  }\>[]

A list of session data objects

### `getSettings`

`GET` **`/session/:sessionId/appium/settings`**

Update the session's settings dictionary with a new settings object

<!-- comment source: method-signature -->

#### Response

``null``

### `updateSettings`

`POST` **`/session/:sessionId/appium/settings`**

Update the session's settings dictionary with a new settings object

<!-- comment source: method-signature -->

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `settings` | `StringRecord` | A key-value map of setting names to values. Settings not named in the map will not have their value adjusted. |

#### Response

``null``

### `getStatus`

`GET` **`/status`**

**`Summary`**

Retrieve the server's current status.

**`Description`**

Returns information about whether a remote end is in a state in which it can create new sessions and can additionally include arbitrary meta information that is specific to the implementation.

The readiness state is represented by the ready property of the body, which is false if an attempt to create a session at the current time would fail. However, the value true does not guarantee that a New Session command will succeed.

Implementations may optionally include additional meta information as part of the body, but the top-level properties ready and message are reserved and must not be overwritten.

<!-- comment source: builtin-interface -->

#### Examples

<!-- BEGIN:EXAMPLES -->
##### JavaScript
<!-- BEGIN:EXAMPLE lang=JavaScript -->

```js
// webdriver.io example
await driver.status();
```

<!-- END:EXAMPLE -->
##### Python
<!-- BEGIN:EXAMPLE lang=Python -->

```python
driver.get_status()
```

<!-- END:EXAMPLE -->
##### Java
<!-- BEGIN:EXAMPLE lang=Java -->

```java
driver.getStatus();
```

<!-- END:EXAMPLE -->
##### Ruby
<!-- BEGIN:EXAMPLE lang=Ruby -->

```ruby
# ruby_lib example
remote_status

# ruby_lib_core example
@driver.remote_status
```

<!-- END:EXAMPLE -->
<!-- END:EXAMPLES -->

#### Response

`Object`

### `getTimeouts`

`GET` **`/session/:sessionId/timeouts`**

Set the various timeouts associated with a session

**`See`**

[https://w3c.github.io/webdriver/#set-timeouts](https://w3c.github.io/webdriver/#set-timeouts)

<!-- comment source: method-signature -->

#### Response

``null``

### `timeouts`

`POST` **`/session/:sessionId/timeouts`**

Set the various timeouts associated with a session

**`See`**

[https://w3c.github.io/webdriver/#set-timeouts](https://w3c.github.io/webdriver/#set-timeouts)

<!-- comment source: method-signature -->

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `type?` | `string` | used only for the old (JSONWP) command, the type of the timeout |
| `ms?` | `string` \| `number` | used only for the old (JSONWP) command, the ms for the timeout |
| `script?` | `number` | the number in ms for the script timeout, used for the W3C command |
| `pageLoad?` | `number` | the number in ms for the pageLoad timeout, used for the W3C command |
| `implicit?` | `string` \| `number` | the number in ms for the implicit wait timeout, used for the W3C command |

#### Response

``null``

### `implicitWait`

`POST` **`/session/:sessionId/timeouts/implicit_wait`**

Set the implicit wait timeout

**`Deprecated`**

Use `timeouts` instead

<!-- comment source: method-signature -->

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `ms` | `string` \| `number` | the timeout in ms |

#### Response

``null``

### `logCustomEvent`

`POST` **`/session/:sessionId/appium/log_event`**

Add a custom-named event to the Appium event log

<!-- comment source: method-signature -->

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `vendor` | `string` | the name of the vendor or tool the event belongs to, to namespace the event |
| `event` | `string` | the name of the event itself |

#### Response

``null``

### `reset`

`POST` **`/session/:sessionId/appium/app/reset`**

Reset the current session (run the delete session and create session subroutines)

**`Deprecated`**

Use explicit session management commands instead

<!-- comment source: method-signature -->

#### Response

``null``

## Execute Methods

### `fake: addition`

#### Route

`POST /session/:sessionId/execute`

#### Parameters

| Name | Type |
| :------ | :------ |
| `num1` | `number` |
| `num2` | `number` |
| `num3?` | `number` |

#### Response

`number`

### `fake: getDeprecatedCommandsCalled`

This is a command that will return a list of deprecated command names called

<!-- comment source: method-signature -->

#### Route

`POST /session/:sessionId/execute`

#### Response

`string`[]

### `fake: getThing`

Gets a thing (a fake thing)

<!-- comment source: other-comment -->

#### Route

`POST /session/:sessionId/execute`

#### Response

``null`` \| `Thing`

### `fake: setThing`

Set the 'thing' value (so that it can be retrieved later)

<!-- comment source: method-signature -->

#### Route

`POST /session/:sessionId/execute`

#### Parameters

| Name | Type |
| :------ | :------ |
| `thing` | `Thing` |

#### Response

``null``
