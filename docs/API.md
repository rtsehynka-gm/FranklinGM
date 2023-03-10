## Classes

<dl>
<dt><a href="#Sidekick">Sidekick</a> ⇐ <code>HTMLElement</code></dt>
<dd><p>The sidekick provides helper tools for authors.</p>
</dd>
</dl>

## Typedefs

<dl>
<dt><a href="#elemAttr">elemAttr</a> : <code>Object.&lt;string, string&gt;</code></dt>
<dd><p>The name and value of the attribute to set on an element.</p>
</dd>
<dt><a href="#elemLstnr">elemLstnr</a> : <code>Object.&lt;string, function()&gt;</code></dt>
<dd><p>The event name and listener to register on an element.</p>
</dd>
<dt><a href="#elemConfig">elemConfig</a> : <code>Object</code></dt>
<dd><p>The configuration of an element to add.</p>
</dd>
<dt><a href="#pluginButton">pluginButton</a> : <code>Object</code></dt>
<dd><p>The configuration for a plugin button. This can be used as
a shorthand for <a href="#elemConfig">elemConfig</a>.</p>
</dd>
<dt><a href="#plugin">plugin</a> : <code>Object</code></dt>
<dd><p>The plugin configuration.</p>
</dd>
<dt><a href="#viewCallback">viewCallback</a> : <code>function</code></dt>
<dd><p>A callback function to render a view.</p>
</dd>
<dt><a href="#viewConfig">viewConfig</a> : <code>Object</code></dt>
<dd><p>A custom view configuration.</p>
</dd>
<dt><a href="#helpStep">helpStep</a> : <code>Object</code></dt>
<dd><p>The definition of a help step inside a <a href="#helpTopic">helpTopic</a>.</p>
</dd>
<dt><a href="#helpTopic">helpTopic</a> : <code>Object</code></dt>
<dd><p>The definition of a help topic.</p>
</dd>
<dt><a href="#sidekickConfig">sidekickConfig</a> : <code>Object</code></dt>
<dd><p>The sidekick configuration.</p>
</dd>
</dl>

## External

<dl>
<dt><a href="#external_window.hlx.sidekickConfig">window.hlx.sidekickConfig</a> : <code><a href="#sidekickConfig">sidekickConfig</a></code></dt>
<dd><p>The global variable holding the initial sidekick configuration.</p>
</dd>
<dt><a href="#external_window.hlx.sidekick">window.hlx.sidekick</a> : <code><a href="#Sidekick">Sidekick</a></code></dt>
<dd><p>The global variable referencing the <a href="#Sidekick">Sidekick</a> singleton.</p>
</dd>
<dt><a href="#external_window.hlx.sidekickScript">window.hlx.sidekickScript</a> : <code>Element</code></dt>
<dd><p>The <pre>script</pre> element which loaded the sidekick module.</p>
</dd>
<dt><a href="#external_window.hlx.initSidekick">window.hlx.initSidekick</a> ⇒ <code><a href="#Sidekick">Sidekick</a></code></dt>
<dd><p>Initializes the sidekick and stores a reference to it in
             <a href="window.hlx.sidekick">window.hlx.sidekick</a>.</p>
</dd>
</dl>

<a name="Sidekick"></a>

## Sidekick ⇐ <code>HTMLElement</code>
The sidekick provides helper tools for authors.

**Kind**: global class  
**Extends**: <code>HTMLElement</code>  

* [Sidekick](#Sidekick) ⇐ <code>HTMLElement</code>
    * [new Sidekick(cfg)](#new_Sidekick_new)
    * [.fetchStatus()](#Sidekick+fetchStatus) ⇒ [<code>Sidekick</code>](#Sidekick)
    * [.loadContext(cfg)](#Sidekick+loadContext) ⇒ [<code>Sidekick</code>](#Sidekick)
    * [.checkPushDownContent()](#Sidekick+checkPushDownContent) ⇒ [<code>Sidekick</code>](#Sidekick)
    * [.show()](#Sidekick+show) ⇒ [<code>Sidekick</code>](#Sidekick)
    * [.hide()](#Sidekick+hide) ⇒ [<code>Sidekick</code>](#Sidekick)
    * [.toggle()](#Sidekick+toggle) ⇒ [<code>Sidekick</code>](#Sidekick)
    * [.add(plugin)](#Sidekick+add) ⇒ <code>HTMLElement</code>
    * [.get(id)](#Sidekick+get) ⇒ <code>HTMLElement</code>
    * [.remove(id)](#Sidekick+remove) ⇒ [<code>Sidekick</code>](#Sidekick)
    * [.isEditor()](#Sidekick+isEditor) ⇒ <code>boolean</code>
    * [.isDev()](#Sidekick+isDev) ⇒ <code>boolean</code>
    * [.isInner()](#Sidekick+isInner) ⇒ <code>boolean</code>
    * [.isOuter()](#Sidekick+isOuter) ⇒ <code>boolean</code>
    * [.isProd()](#Sidekick+isProd) ⇒ <code>boolean</code>
    * [.isFranklin()](#Sidekick+isFranklin) ⇒ <code>boolean</code>
    * ~~[.isHelix()](#Sidekick+isHelix) ⇒ <code>boolean</code>~~
    * [.isContent()](#Sidekick+isContent) ⇒ <code>boolean</code>
    * [.isAuthenticated()](#Sidekick+isAuthenticated) ⇒ <code>boolean</code>
    * [.isAuthorized(feature, permission)](#Sidekick+isAuthorized) ⇒ <code>boolean</code>
    * ~~[.notify(message, level)](#Sidekick+notify)~~
    * [.showWait()](#Sidekick+showWait)
    * [.showModal(msg, sticky, level, callback)](#Sidekick+showModal) ⇒ [<code>Sidekick</code>](#Sidekick)
    * [.hideModal()](#Sidekick+hideModal) ⇒ [<code>Sidekick</code>](#Sidekick)
    * [.showHelp(topic, step)](#Sidekick+showHelp) ⇒ [<code>Sidekick</code>](#Sidekick)
    * [.loadCSS(path)](#Sidekick+loadCSS) ⇒ [<code>Sidekick</code>](#Sidekick)
    * [.switchEnv(targetEnv, open)](#Sidekick+switchEnv) ⇒ [<code>Sidekick</code>](#Sidekick)
    * [.update()](#Sidekick+update) ⇒ <code>Response</code>
    * [.delete()](#Sidekick+delete) ⇒ <code>Response</code>
    * [.publish(path)](#Sidekick+publish) ⇒ <code>Response</code>
    * [.unpublish()](#Sidekick+unpublish) ⇒ <code>Response</code>
    * [.addEventListener(type, listener, opts)](#Sidekick+addEventListener)
    * [.removeEventListener(type, listener)](#Sidekick+removeEventListener)
    * ["shown"](#Sidekick+event_shown)
    * ["hidden"](#Sidekick+event_hidden)
    * ["pluginused"](#Sidekick+event_pluginused)
    * ["contextloaded"](#Sidekick+event_contextloaded)
    * ["statusfetched"](#Sidekick+event_statusfetched)
    * ["envswitched"](#Sidekick+event_envswitched)
    * ["updated"](#Sidekick+event_updated)
    * ["deleted"](#Sidekick+event_deleted)
    * ["published"](#Sidekick+event_published)
    * ["unpublished"](#Sidekick+event_unpublished)
    * ["loggedin"](#Sidekick+event_loggedin)
    * ["loggedout"](#Sidekick+event_loggedout)
    * ["helpnext"](#Sidekick+event_helpnext)
    * ["helpdismissed"](#Sidekick+event_helpdismissed)
    * ["helpacknowledged"](#Sidekick+event_helpacknowledged)
    * ["helpoptedout"](#Sidekick+event_helpoptedout)

<a name="new_Sidekick_new"></a>

### new Sidekick(cfg)
Creates a new sidekick.


| Param | Type | Description |
| --- | --- | --- |
| cfg | [<code>sidekickConfig</code>](#sidekickConfig) | The sidekick config |

<a name="Sidekick+fetchStatus"></a>

### sidekick.fetchStatus() ⇒ [<code>Sidekick</code>](#Sidekick)
Fetches the status for the current resource.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: [<code>Sidekick</code>](#Sidekick) - The sidekick  
**Emits**: [<code>statusfetched</code>](#Sidekick+event_statusfetched)  
<a name="Sidekick+loadContext"></a>

### sidekick.loadContext(cfg) ⇒ [<code>Sidekick</code>](#Sidekick)
Loads the sidekick configuration and retrieves the location of the current document.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: [<code>Sidekick</code>](#Sidekick) - The sidekick  
**Emits**: [<code>contextloaded</code>](#Sidekick+event_contextloaded)  

| Param | Type | Description |
| --- | --- | --- |
| cfg | [<code>sidekickConfig</code>](#sidekickConfig) | The sidekick config |

<a name="Sidekick+checkPushDownContent"></a>

### sidekick.checkPushDownContent() ⇒ [<code>Sidekick</code>](#Sidekick)
Recalculates the height of the sidekick and pushes down the
page content by that amount to make room for the sidekick.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: [<code>Sidekick</code>](#Sidekick) - The sidekick  
<a name="Sidekick+show"></a>

### sidekick.show() ⇒ [<code>Sidekick</code>](#Sidekick)
Shows the sidekick.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: [<code>Sidekick</code>](#Sidekick) - The sidekick  
**Emits**: [<code>shown</code>](#Sidekick+event_shown)  
<a name="Sidekick+hide"></a>

### sidekick.hide() ⇒ [<code>Sidekick</code>](#Sidekick)
Hides the sidekick.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: [<code>Sidekick</code>](#Sidekick) - The sidekick  
**Emits**: [<code>hidden</code>](#Sidekick+event_hidden)  
<a name="Sidekick+toggle"></a>

### sidekick.toggle() ⇒ [<code>Sidekick</code>](#Sidekick)
Shows/hides the sidekick.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: [<code>Sidekick</code>](#Sidekick) - The sidekick  
<a name="Sidekick+add"></a>

### sidekick.add(plugin) ⇒ <code>HTMLElement</code>
Adds a plugin to the sidekick.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>HTMLElement</code> - The plugin  

| Param | Type | Description |
| --- | --- | --- |
| plugin | [<code>plugin</code>](#plugin) | The plugin configuration. |

<a name="Sidekick+get"></a>

### sidekick.get(id) ⇒ <code>HTMLElement</code>
Returns the sidekick plugin with the specified ID.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>HTMLElement</code> - The plugin  

| Param | Type | Description |
| --- | --- | --- |
| id | <code>string</code> | The plugin ID |

<a name="Sidekick+remove"></a>

### sidekick.remove(id) ⇒ [<code>Sidekick</code>](#Sidekick)
Removes the plugin with the specified ID from the sidekick.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: [<code>Sidekick</code>](#Sidekick) - The sidekick  

| Param | Type | Description |
| --- | --- | --- |
| id | <code>string</code> | The plugin ID |

<a name="Sidekick+isEditor"></a>

### sidekick.isEditor() ⇒ <code>boolean</code>
Checks if the current location is an editor URL (SharePoint or Google Docs).

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>boolean</code> - <code>true</code> if editor URL, else <code>false</code>  
<a name="Sidekick+isDev"></a>

### sidekick.isDev() ⇒ <code>boolean</code>
Checks if the current location is a development URL.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>boolean</code> - <code>true</code> if development URL, else <code>false</code>  
<a name="Sidekick+isInner"></a>

### sidekick.isInner() ⇒ <code>boolean</code>
Checks if the current location is an inner CDN URL.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>boolean</code> - <code>true</code> if inner CDN URL, else <code>false</code>  
<a name="Sidekick+isOuter"></a>

### sidekick.isOuter() ⇒ <code>boolean</code>
Checks if the current location is an outer CDN URL.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>boolean</code> - <code>true</code> if outer CDN URL, else <code>false</code>  
<a name="Sidekick+isProd"></a>

### sidekick.isProd() ⇒ <code>boolean</code>
Checks if the current location is a production URL.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>boolean</code> - <code>true</code> if production URL, else <code>false</code>  
<a name="Sidekick+isFranklin"></a>

### sidekick.isFranklin() ⇒ <code>boolean</code>
Checks if the current location is a configured Franklin URL.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>boolean</code> - <code>true</code> if Franklin URL, else <code>false</code>  
<a name="Sidekick+isHelix"></a>

### ~~sidekick.isHelix() ⇒ <code>boolean</code>~~
***Deprecated***

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>boolean</code> - <code>true</code> if Franklin URL, else <code>false</code>  
<a name="Sidekick+isContent"></a>

### sidekick.isContent() ⇒ <code>boolean</code>
Checks if the current location is a content URL.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>boolean</code> - <code>true</code> if content URL, else <code>false</code>  
<a name="Sidekick+isAuthenticated"></a>

### sidekick.isAuthenticated() ⇒ <code>boolean</code>
Checks if the user is logged in.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>boolean</code> - <code>true</code> if user is logged in (or does not need to be),
else <code>false</code>  
<a name="Sidekick+isAuthorized"></a>

### sidekick.isAuthorized(feature, permission) ⇒ <code>boolean</code>
Checks if the user is allowed to use a feature.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>boolean</code> - <code>true</code> if user is allowed, else <code>false</code>  

| Param | Type | Description |
| --- | --- | --- |
| feature | <code>string</code> | The feature to check |
| permission | <code>string</code> | The permission to require |

<a name="Sidekick+notify"></a>

### ~~sidekick.notify(message, level)~~
***Deprecated***

Displays a non-sticky notification.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| message | <code>string</code> \| <code>Array.&lt;string&gt;</code> |  | The message (lines) to display |
| level | <code>number</code> | <code>2</code> | error (0), warning (1), of info (2) |

<a name="Sidekick+showWait"></a>

### sidekick.showWait()
Displays a sticky notification asking the user to wait.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
<a name="Sidekick+showModal"></a>

### sidekick.showModal(msg, sticky, level, callback) ⇒ [<code>Sidekick</code>](#Sidekick)
Displays a modal notification.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: [<code>Sidekick</code>](#Sidekick) - The sidekick  
**Emits**: <code>Sidekick#event:modalshown</code>  

| Param | Type | Description |
| --- | --- | --- |
| msg | <code>object</code> \| <code>string</code> \| <code>Array.&lt;string&gt;</code> | The message (object or lines) |
| msg.message | <code>string</code> | The message |
| msg.css | <code>string</code> | The CSS class to add |
| msg.sticky | <code>boolean</code> | <code>true</code> if message should be sticky (optional) |
| msg.level | <code>number</code> | error (0), warning (1), of info (2, default) |
| msg.callback | <code>function</code> | The function to call when the modal is hidden again |
| sticky | <code>boolean</code> | <code>true</code> if message should be sticky (optional) |
| level | <code>number</code> | error (0), warning (1), of info (2, default) |
| callback | <code>function</code> | The function to call when the modal is hidden again |

<a name="Sidekick+hideModal"></a>

### sidekick.hideModal() ⇒ [<code>Sidekick</code>](#Sidekick)
Hides the modal if shown.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: [<code>Sidekick</code>](#Sidekick) - The sidekick  
**Emits**: <code>Sidekick#event:modalhidden</code>  
<a name="Sidekick+showHelp"></a>

### sidekick.showHelp(topic, step) ⇒ [<code>Sidekick</code>](#Sidekick)
Displays a balloon with help content.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: [<code>Sidekick</code>](#Sidekick) - The sidekick  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| topic | [<code>helpTopic</code>](#helpTopic) |  | The topic |
| step | <code>number</code> | <code>0</code> | The step number to display (starting with 0) |

<a name="Sidekick+loadCSS"></a>

### sidekick.loadCSS(path) ⇒ [<code>Sidekick</code>](#Sidekick)
Loads the specified default CSS file, or a sibling of the
current JS or HTML file. E.g. when called without argument from
/foo/bar.js, it will attempt to load /foo/bar.css.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: [<code>Sidekick</code>](#Sidekick) - The sidekick  

| Param | Type | Description |
| --- | --- | --- |
| path | <code>string</code> | The path to the CSS file (optional) |

<a name="Sidekick+switchEnv"></a>

### sidekick.switchEnv(targetEnv, open) ⇒ [<code>Sidekick</code>](#Sidekick)
Switches to (or opens) a given environment.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: [<code>Sidekick</code>](#Sidekick) - The sidekick  
**Emits**: [<code>envswitched</code>](#Sidekick+event_envswitched)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| targetEnv | <code>string</code> |  | One of the following environments:        <pre>dev</pre>, <pre>preview</pre>, <pre>live</pre> or <pre>prod</pre> |
| open | <code>boolean</code> | <code>false</code> | <pre>true</pre> if environment should be opened in new tab |

<a name="Sidekick+update"></a>

### sidekick.update() ⇒ <code>Response</code>
Updates the preview or code of the current resource.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>Response</code> - The response object  
**Emits**: [<code>updated</code>](#Sidekick+event_updated)  
<a name="Sidekick+delete"></a>

### sidekick.delete() ⇒ <code>Response</code>
Deletes the preview or code of the current resource.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>Response</code> - The response object  
**Emits**: [<code>deleted</code>](#Sidekick+event_deleted)  
<a name="Sidekick+publish"></a>

### sidekick.publish(path) ⇒ <code>Response</code>
Publishes the page at the specified path if <pre>config.host</pre> is defined.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>Response</code> - The response object  
**Emits**: [<code>published</code>](#Sidekick+event_published)  

| Param | Type | Description |
| --- | --- | --- |
| path | <code>string</code> | The path of the page to publish |

<a name="Sidekick+unpublish"></a>

### sidekick.unpublish() ⇒ <code>Response</code>
Unpublishes the current page.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  
**Returns**: <code>Response</code> - The response object  
**Emits**: [<code>unpublished</code>](#Sidekick+event_unpublished)  
<a name="Sidekick+addEventListener"></a>

### sidekick.addEventListener(type, listener, opts)
Sets up a function that will be called whenever the specified sidekick
event is fired.

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  

| Param | Type | Description |
| --- | --- | --- |
| type | <code>string</code> | The event type |
| listener | <code>function</code> | The function to call |
| opts | <code>object</code> | options |

<a name="Sidekick+removeEventListener"></a>

### sidekick.removeEventListener(type, listener)
Removes an event listener previously registered with [addEventListener](addEventListener).

**Kind**: instance method of [<code>Sidekick</code>](#Sidekick)  

| Param | Type | Description |
| --- | --- | --- |
| type | <code>string</code> | The event type |
| listener | <code>function</code> | The function to remove |

<a name="Sidekick+event_shown"></a>

### "shown"
This event is fired when the sidekick has been shown.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
<a name="Sidekick+event_hidden"></a>

### "hidden"
This event is fired when the sidekick has been hidden.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
<a name="Sidekick+event_pluginused"></a>

### "pluginused"
This event is fired when a sidekick plugin has been used.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| id | <code>string</code> | The plugin ID |
| button | <code>Element</code> | The button element |

<a name="Sidekick+event_contextloaded"></a>

### "contextloaded"
This event is fired when the context has been loaded.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| config | [<code>sidekickConfig</code>](#sidekickConfig) | The sidekick configuration |
| location | <code>Location</code> | The sidekick location |

<a name="Sidekick+event_statusfetched"></a>

### "statusfetched"
This event is fired when the status has been fetched.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
<a name="Sidekick+event_envswitched"></a>

### "envswitched"
This event is fired when the environment has been switched

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| sourceUrl | <code>string</code> | The URL of the source environment |
| targetUrl | <code>string</code> | The URL of the target environment |

<a name="Sidekick+event_updated"></a>

### "updated"
This event is fired when a path has been updated.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
<a name="Sidekick+event_deleted"></a>

### "deleted"
This event is fired when a path has been deleted.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
<a name="Sidekick+event_published"></a>

### "published"
This event is fired when a path has been published.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
<a name="Sidekick+event_unpublished"></a>

### "unpublished"
This event is fired when a path has been unpublished.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
<a name="Sidekick+event_loggedin"></a>

### "loggedin"
This event is fired when a user has logged in.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
<a name="Sidekick+event_loggedout"></a>

### "loggedout"
This event is fired when a user has logged out.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
<a name="Sidekick+event_helpnext"></a>

### "helpnext"
This event is fired when a user clicks next on a help dialog.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
<a name="Sidekick+event_helpdismissed"></a>

### "helpdismissed"
This event is fired when a help dialog has been dismissed.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
<a name="Sidekick+event_helpacknowledged"></a>

### "helpacknowledged"
This event is fired when a help dialog has been acknowledged.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
<a name="Sidekick+event_helpoptedout"></a>

### "helpoptedout"
This event is fired when a user decides to opt out of help content.

**Kind**: event emitted by [<code>Sidekick</code>](#Sidekick)  
<a name="elemAttr"></a>

## elemAttr : <code>Object.&lt;string, string&gt;</code>
The name and value of the attribute to set on an element.

**Kind**: global typedef  
<a name="elemLstnr"></a>

## elemLstnr : <code>Object.&lt;string, function()&gt;</code>
The event name and listener to register on an element.

**Kind**: global typedef  
<a name="elemConfig"></a>

## elemConfig : <code>Object</code>
The configuration of an element to add.

**Kind**: global typedef  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| tag | <code>string</code> | The tag name (mandatory) |
| text | <code>string</code> | The text content (optional) |
| attrs | [<code>Array.&lt;elemAttr&gt;</code>](#elemAttr) | The attributes (optional) |
| lstnrs | [<code>Array.&lt;elemLstnr&gt;</code>](#elemLstnr) | The event listeners (optional) |

<a name="pluginButton"></a>

## pluginButton : <code>Object</code>
The configuration for a plugin button. This can be used as
a shorthand for [elemConfig](#elemConfig).

**Kind**: global typedef  
**Properties**

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | The button text |
| action | <code>function</code> |  | The click listener |
| isPressed | <code>function</code> | <code>false</code> | Determines whether the button is pressed |
| isEnabled | <code>function</code> | <code>true</code> | Determines whether to enable the button |
| isDropdown | <code>boolean</code> | <code>false</code> | Determines whether to turn this button into a dropdown |

<a name="plugin"></a>

## plugin : <code>Object</code>
The plugin configuration.

**Kind**: global typedef  
**Properties**

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| id | <code>string</code> |  | The plugin ID (mandatory) |
| button | [<code>pluginButton</code>](#pluginButton) |  | A button configuration object (optional) |
| container | <code>string</code> |  | The ID of a dropdown to add this plugin to (optional) |
| override | <code>boolean</code> | <code>false</code> | Determines whether to replace an existing plugin |
| elements | [<code>Array.&lt;elemConfig&gt;</code>](#elemConfig) |  | An array of elements to add (optional) |
| condition | <code>function</code> |  | Determines whether to show this plugin (optional). This function is expected to return a boolean when called with the sidekick as argument. |
| advanced | <code>function</code> |  | Show this plugin only in advanced mode (optional). This function is expected to return a boolean when called with the sidekick as argument. |
| callback | <code>function</code> |  | A function called after adding the plugin (optional). This function is called with the sidekick and the newly added plugin as arguments. |

<a name="viewCallback"></a>

## viewCallback : <code>function</code>
A callback function to render a view.

**Kind**: global typedef  

| Param | Type | Description |
| --- | --- | --- |
| viewContainer | <code>HTMLELement</code> | The view container |
| data | <code>Object</code> | The data to display |

<a name="viewConfig"></a>

## viewConfig : <code>Object</code>
A custom view configuration.

**Kind**: global typedef  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| js | <code>string</code> \| [<code>viewCallback</code>](#viewCallback) | The URL of a JS module or a function to render this view |
| path | <code>string</code> | The path or globbing pattern where to apply this view |
| css | <code>string</code> | The URL of a CSS file or inline CSS to render this view (optional) |

<a name="helpStep"></a>

## helpStep : <code>Object</code>
The definition of a help step inside a [helpTopic](#helpTopic).

**Kind**: global typedef  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| message | <code>string</code> | The help message |
| selector | <code>string</code> | The CSS selector of the target element |

<a name="helpTopic"></a>

## helpTopic : <code>Object</code>
The definition of a help topic.

**Kind**: global typedef  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| id | <code>string</code> | The ID of the help topic |
| steps | [<code>Array.&lt;helpStep&gt;</code>](#helpStep) | An array of [helpStep](#helpStep)s |

<a name="sidekickConfig"></a>

## sidekickConfig : <code>Object</code>
The sidekick configuration.

**Kind**: global typedef  
**Properties**

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| owner | <code>string</code> |  | The GitHub owner or organization (mandatory) |
| repo | <code>string</code> |  | The GitHub owner or organization (mandatory) |
| ref | <code>string</code> | <code>&quot;main&quot;</code> | The Git reference or branch (optional) |
| mountpoint | <code>string</code> |  | The content source URL (optional) |
| project | <code>string</code> |  | The name of the Franklin project used in the sharing link (optional) |
| plugins | [<code>Array.&lt;plugin&gt;</code>](#plugin) |  | An array of plugin configurations (optional) |
| outerHost | <code>string</code> |  | The outer CDN's host name (optional) |
| host | <code>string</code> |  | The production host name to publish content to (optional) |
| byocdn | <code>boolean</code> | <code>false</code> | <pre>true</pre> if the production host is a 3rd party CDN |
| devMode | <code>boolean</code> | <code>false</code> | Loads configuration and plugins from the developmemt environment |
| pushDown | <code>boolean</code> | <code>false</code> | <pre>true</pre> to have the sidekick push down page content |
| pushDownSelector | <code>string</code> |  | The CSS selector for absolute elements to also push down |
| specialViews | [<code>Array.&lt;viewConfig&gt;</code>](#viewConfig) |  | An array of custom view configurations (optional) |
| adminVersion | <code>number</code> |  | The specific version of admin service to use (optional) |

<a name="external_window.hlx.sidekickConfig"></a>

## window.hlx.sidekickConfig : [<code>sidekickConfig</code>](#sidekickConfig)
The global variable holding the initial sidekick configuration.

**Kind**: global external  
<a name="external_window.hlx.sidekick"></a>

## window.hlx.sidekick : [<code>Sidekick</code>](#Sidekick)
The global variable referencing the [Sidekick](#Sidekick) singleton.

**Kind**: global external  
<a name="external_window.hlx.sidekickScript"></a>

## window.hlx.sidekickScript : <code>Element</code>
The <pre>script</pre> element which loaded the sidekick module.

**Kind**: global external  
<a name="external_window.hlx.initSidekick"></a>

## window.hlx.initSidekick ⇒ [<code>Sidekick</code>](#Sidekick)
Initializes the sidekick and stores a reference to it in
             [window.hlx.sidekick](window.hlx.sidekick).

**Kind**: global external  
**Returns**: [<code>Sidekick</code>](#Sidekick) - The sidekick  

| Param | Type | Description |
| --- | --- | --- |
| cfg | [<code>sidekickConfig</code>](#sidekickConfig) | The sidekick configuration        (extends [window.hlx.sidekickConfig](window.hlx.sidekickConfig)) |

