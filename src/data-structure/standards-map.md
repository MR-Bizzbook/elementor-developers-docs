# Elementor Docs Standards Data Structure

This file consolidates the documentation standards across all Elementor developer docs pages into one reference map.

- Total sections: **23**
- Total documents: **293**

## Canonical Structure (JSON shape)

```json
{
  "section": "string",
  "docs": [
    {
      "title": "string",
      "path": "src/<section>/<file>.md",
      "summary": "string"
    }
  ]
}
```

## addons (9 docs)

| Standard | Path | Summary |
|---|---|---|
| Addon Wrapper Example | `addons/addon-example.md` | Let’s create a wrapper for Elementor addons that incorporates everything we’ve learned so far -a file/folder structure, the basic header comments required for every WordPress plugin, namespaces, and compatibility checks. |
| Compatibility Checks | `addons/compatibility.md` | Before initializing, the addon should check that its basic requirements are met. If these requirements are not met, the addon shouldn’t run. |
| File & Folder Structure | `addons/file-folder-structure.md` | All [WordPress plugin guidelines](https://developer.wordpress.org/plugins/plugin-basics/best-practices/#file-organization) should be applied to Elementor addons. You should keep your folder structure simple and place similar files together. |
| Building Addons | `addons/index.md` | Elementor addons are basically WordPress plugins that add functionality to Elementor. Before you start creating Elementor addons, you need a background in creating WordPress plugins. Afterwards, you need to learn the basics of how Elementor addons are built. |
| Initialization Process | `addons/initialization.md` | After passing all compatibility checks, we can safely run the addon and start extending Elementor's functionality. We can load other files, hook to filters and actions and write custom code. |
| Loading Process | `addons/load.md` | Now that we have a WordPress plugin with all the header comments containing the basic information, we need to load the actual functionality. We should tell WordPress to load our functionality once activated plugins have been loaded. This is important as we need to make sure Elementor is loaded. |
| Main Class | `addons/main-class.md` | We can move the different components into a single class - our main class. It should check basic requirements and load the files required to activate the addon's functionality, and then load the various components. |
| Using Namespaces | `addons/namespaces.md` | PHP namespaces are a way of encapsulating your addon's functionality. Just like the filesystem, the namespace system can make your code organized and easy to use. |
| Header Comments | `addons/plugin-header.md` | Header comments are the standard way WordPress uses to provide information about plugins. The addon's main PHP file should include a header comment with basic information. Addons can also add optional Elementor header comments. |

## cli (19 docs)

| Standard | Path | Summary |
|---|---|---|
| Composer | `cli/composer.md` | Developers can install Elementor and Elementor Pro via [Composer](https://getcomposer.org/) instead of using a web browser. It can be done using a few simple CLI commands. |
| Experiment Activation | `cli/experiments-activate.md` | Elementor provides access to new and experimental features before they're officially released. Experiments can be activated from the admin panel or from the command line using the `experiments activate` command. |
| Experiment Deactivation | `cli/experiments-deactivate.md` | Elementor users can access experimental features which have not been officially released. Those experiments can be deactivated from the admin panel or from the command line using the `experiments deactivate` command. |
| Experiment Status | `cli/experiments-status.md` | Elementor experimental features can be used before they're officially released. To check from the command line whether an experimental feature is active or inactive, use the `experiments status` command. |
| Flush CSS | `cli/flush-css.md` | Styles set in Elementor are saved in the database, this information is used to generate CSS files in `/wp-content/uploads/elementor/css/` folder. Elementor CLI `flush-css` command will delete all the cached CSS files and recreate them using the most recent settings stored in the database. |
| Elementor CLI | `cli/index.md` | Elementor integrates with [WP-CLI](https://wp-cli.org/), enabling you to run certain Elementor tasks via the command line interface, without using a web browser. |
| Kit Export | `cli/kit-export.md` | Exporting multiple individual templates is not an easy task. Elementor can export all of a site's content, templates, and site settings bundled as a kit. These kits can be exported from the admin panel or from the command line using the `kit export` command. |
| Kit Import | `cli/kit-import.md` | An Elementor kit is a bundle of templates, pages, popups, etc. Rather than importing each template individually you can import all the content at once. A kit can be imported from the admin panel or from the command line using the `kit import` command. |
| Library Connect | `cli/library-connect.md` | Connect a site to the Elementor library from the command line by simply providing a WordPress user and a connection token. |
| Library Disconnect | `cli/library-disconnect.md` | Disconnect a site from the Elementor library using the command line, by simply providing the WordPress user. |
| Library Import Dir | `cli/library-import-dir.md` | Importing templates one by one is time consuming. You can import all the templates in a directory at once. Elementor CLI `library import-dir` command will import all the template JSON files using the command line. |
| Library Import | `cli/library-import.md` | Users can import Elementor templates from the library by uploading a single template JSON file or a ZIP file with multiple JSON files. The Elementor CLI `library import` command will import the template using the command line. |
| Library Sync | `cli/library-sync.md` | Elementor holds, locally, a list of available templates that can be downloaded from the Elementor template library. A transient is scheduled to synch the available templates every 12 hours. Elementor CLI `library sync` command triggers this sync from the cloud using the command line. |
| License Activation | `cli/license-activate.md` | Elementor Pro is a premium product that requires a license. To activate the license for a site you need a valid license key. A license can be activated from the admin panel or from the command line using the `license activate` command. |
| License Deactivation | `cli/license-deactivate.md` | Some Elementor Pro licenses can activate multiple sites. If no more activations are left on a license, you can deactivate some sites to free up more activations. You can deactivate a site from the admin panel or from the command line using the `license deactivate` command. |
| Replace URLs | `cli/replace-urls.md` | Sites that change the URL, whether migrating to different domain or simple transfering from HTTP to HTTPs, need to update URLs in the database. Elementor has a tool that replaces old URLs with new URLs in all Elementor pages. The Elementor CLI `replace-urls` command will do exactly that. |
| System Info | `cli/system-info.md` | System info shows details about the website configuration. This data can be used to debug issues, helping developers and support engineers identify problems. The Elementor CLI `system info` command will print the site's system info in a JSON format. |
| Clear Theme Builder Conditions | `cli/theme-builder-clear-conditions.md` | The Elementor theme-builder is used to create site part templates. These templates can be applied based on predefined conditions. All the conditions are cached. The Elementor CLI `theme-builder clear-conditions` command will clear the cached conditions to trigger a regeneration process. |
| Update DB | `cli/update-db.md` | In some cases, new Elementor versions perform changes in the database (e.g. migrate to kits, replace schemes with globals etc.). Elementor CLI `update db` command will trigger the database update functionality using the command line. |

## context-menu (12 docs)

| Standard | Path | Summary |
|---|---|---|
| Add New Action | `context-menu/add-new-action.md` | To add a new action to the context menu, we need to define a new action object and insert the object into the relevant context menu group. |
| Add New Group | `context-menu/add-new-group.md` | To add a new group to the context menu, we need to define a new group object and insert it into the relevant menu type (i.e. widget, column or section). |
| Advanced Example | `context-menu/advanced-example.md` | In this example, we'll build a full Elementor addon that sends and opens [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/) in a new tab to test page performance. |
| Context Menu Actions | `context-menu/context-menu-actions.md` | The context menu popup contains groups, and within these groups are items called actions. Actions are applied to a selected element (section, column, widget). Behind the scenes, these actions are JS callback functions. |
| Context Menu Groups | `context-menu/context-menu-groups.md` | Context menu popups contain several groups divided by a separator. Each group contains a number of actions - groups are only displayed if they have at least one action. |
| Context Menu Types | `context-menu/context-menu-types.md` | Elementor has several types of context menus based on the selected location or element. To open a context menu the user needs to right click an element or location. As different elements have different functionalities, each menu lists different action items. When modifying an action, developers must indicate which element the action should be applied to. |
| Elementor Context Menu | `context-menu/index.md` | A context menu is a popup menu that appears when users right click an element in the [Elementor preview](./../editor/elementor-preview/) area. This popup menu offers a set of available actions based on location or the selected element. That is why it is called a context menu. |
| Remove Action | `context-menu/remove-action.md` | To remove an existing action from the context menu, we need to delete that action from a group. |
| Remove Group | `context-menu/remove-group.md` | To remove groups from the context menu, we need to check if the group exist in the relevant menu type and delete that group from a context menu. This will delete the entire group with all the actions assigned to this group. |
| Simple Example | `context-menu/simple-example.md` | In this example, we'll build a full Elementor addon to modify a context menu. |
| Update Action | `context-menu/update-action.md` | To modify an existing action, we need to change the action object value in a specific entry. |
| Update Group | `context-menu/update-group.md` | To modify an existing group, we need to change the group object. |

## controls (10 docs)

| Standard | Path | Summary |
|---|---|---|
| Add New Control | `controls/add-new-control.md` | Elementor offers many built-in controls out of the box, but it also allows external developers to register new controls. |
| Complex Example | `controls/complex-example.md` | Now we'll build an addon that adds a new control to Elementor by using an external library. The control will display a textarea field, and we will use the [Emoji One Area](https://github.com/mervick/emojionearea) library to allow the user to add emojis to the content. |
| Control Enqueue | `controls/control-enqueue.md` | Controls can register and enqueue scripts & styles used by the control. |
| Control Settings | `controls/control-settings.md` | **Control settings** allow developers to set defaults for controls such as the label, description, whether or not to show a separator, hide the label, etc. |
| Control Structure | `controls/control-structure.md` | Creating custom controls is a task reserved for advanced Elementor developers who are very familiar with the code base. The process starts with learning the `Base_Control` class, along with its inner methods. This will allow you to understand how Elementor creates different controls and how you can customize these base methods. |
| Control Template | `controls/control-template.md` | The template generates the final HTML displayed in the editor. The template uses JS to return data from the settings using the `data` JS object. |
| Control Values | `controls/control-values.md` | You can set custom default values for your control. For example, if you add a new field, you can define its default value. |
| Elementor Controls | `controls/index.md` | Elementor Controls are **input fields** and **UI elements** that are used to construct an interface. Controls allow users to customize available panel settings and change the design in the preview. |
| Remove Controls | `controls/remove-controls.md` | To remove existing control developers can simply unregister existing control by passing the control name. |
| Simple Example | `controls/simple-example.md` | Let's build an addon that adds a new control to Elementor. The control will display a select field with the ability to choose currencies. |

## data-structure (10 docs)

| Standard | Path | Summary |
|---|---|---|
| Container Element | `data-structure/container-element.md` | The container is a layout element with nested capabilities, meaning that it can hold other elements. The container object contains information like the element id, element type, styling settings and all the element inside the container. |
| General Elements | `data-structure/general-elements.md` | Each Elementor element, whether it's a layout element (section, column, container) or a widget element, has a set of basic information. This data is used to parse the element when creating the page. |
| General Structure | `data-structure/general-structure.md` | The JSON structure consists of an object containing information about the page. The information includes the document type, it's title and the version. Furthermore, it holds real data such as document settings and the document content. |
| Global Styles | `data-structure/global-styles.md` | WIP |
| Data Structure | `data-structure/index.md` | Elementor relies on a particular data structure to function. This structure plays a significant role in the platform's processes and is essential to its operation. Developers should be familiar with the key aspects of Elementor's data structure including its format and application. |
| Page Content | `data-structure/page-content.md` | The page content is an `array` of objects which holds all the elements on the page. This field is recursive, meaning that it can hold nested elements, one inside the other. A container element can contain other containers and widgets, and nested widgets can contain other widgets. |
| Page Settings | `data-structure/page-settings.md` | Data from the [Page Settings](./../editor/page-settings-panel/) panel is saved as a separate `page_settings` value. When the page has no settings, the value is an empty `array`, when the page has settings it's an `object` of key-value pairs containing the settings. |
| Repeaters | `data-structure/repeaters.md` | WIP |
| Responsive Data | `data-structure/responsive-data.md` | WIP |
| Widget Element | `data-structure/widget-element.md` | An Elementor widget is an element with its own custom properties. The widget object contains information like the element id, element type, widget type and all the element settings based on the widget controls. |

## deprecations (8 docs)

| Standard | Path | Summary |
|---|---|---|
| Advanced Example | `deprecations/advanced-example.md` | A common example of deprecation is the [managers](./../managers/) registration process in Elementor 3.5. In this instance, many registration methods and hooks have been standardized and simplified using intuitive naming conventions. |
| Complex Example | `deprecations/complex-example.md` | In Elementor 3.0, the limited Schemes mechanism had been replaced with [Globals](./../editor-controls/global-style/) which allows users to define limitless colors and typographies. Addons using schemes in their widgets controls should update their code. |
| Deprecated Action Hooks | `deprecations/deprecated-action-hook.md` | Elementor offers the `Deprecation::do_deprecated_action()` method to handle the deprecation process for actions hooks inside Elementor code. |
| Deprecated Arguments | `deprecations/deprecated-argument.md` | Elementor offers the `Deprecation::deprecated_argument()` method to handle the deprecation process for arguments inside the Elementor code. |
| Deprecated Filter Hooks | `deprecations/deprecated-filter-hook.md` | Elementor offers the `Deprecation::apply_deprecated_filter()` method to handle the deprecation process for filter hooks inside Elementor code. |
| Deprecated Function | `deprecations/deprecated-function.md` | Elementor offers the `Deprecation::deprecated_function()` method to handle the deprecation process for functions and methods inside Elementor code. |
| Elementor Deprecations | `deprecations/index.md` | Elementor is an evolving product. Over time, code is removed or replaced. These deprecations are announced over various channels. The deprecation process is gradual and deprecated code is only removed after at least 8 major versions. |
| Simple Example | `deprecations/simple-example.md` | One example of commonly used deprecated conventions is when addon developers create [widgets](./../widgets/widget-structure/) using methods with deprecated `_` prefix. Previously, Elementor protected methods prefixed with `_` but that naming convention was deprecated. |

## dynamic-tags (12 docs)

| Standard | Path | Summary |
|---|---|---|
| Add New Dynamic Tag | `dynamic-tags/add-new-dynamic-tag.md` | Elementor offers many built-in dynamic tags out of the box, but it also allows external developers to register new tags. |
| Advanced Example | `dynamic-tags/advanced-example.md` | This more advanced example will include the use of custom fields, and controls where the user can set fields. The tag will calculate the average of those fields and include a single control where the user can set a comma-separated list of ACF field IDs. |
| Complex Example | `dynamic-tags/complex-example.md` | To showcase a complex dynamic tag, we are going to allow the user to display server variables from a list of available server variables. It will include a custom [dynamic tags group](./dynamic-tags-groups/) and feature a control with a select box containing all the available server variables. The render function will return the variable the user selected and return its value. |
| Dynamic Tags Categories | `dynamic-tags/dynamic-tags-categories.md` | When controls are created, developers can define whether the [control can accept dynamic data](./../editor-controls/dynamic-content/) or not. If the control does accept dynamic data, then a data type (e.g. text values, colors, images) must be set. Dynamic tags, on the other hand, need to define what types of data they return to the control. |
| Dynamic Tags Controls | `dynamic-tags/dynamic-tags-controls.md` | Simple tags return dynamic data that have no dependencies, such as a random number. More complex tags may have optional fields where users can configure their custom data, such as a random number where the user can set minimum and maximum values. Later, the render method will use those custom fields to generate the final output. |
| Dynamic Tags Data | `dynamic-tags/dynamic-tags-data.md` | Each dynamic tag requires basic information like the unique ID, title, group and category. |
| Dynamic Tags Groups | `dynamic-tags/dynamic-tags-groups.md` | <img :src="$withBase('/assets/img/dynamic-tags-list.png')" alt="Dynamic Tags List" style="float: right; width: 300px; margin-left: 20px; margin-bottom: 20px;"> |
| Dynamic Tags Rendering | `dynamic-tags/dynamic-tags-rendering.md` | The render method generates the final output and echoes the data to the control. If the dynamic tag has controls, the render function should use the data while generating the output. |
| Dynamic Tags Structure | `dynamic-tags/dynamic-tags-structure.md` | Each dynamic tag needs to have a few basic settings, such as a unique name. On top of that, there are some advanced settings like dynamic tag controls, which are basically optional fields where users can configure their custom data. There is also a render method that generates the final output based on user settings taken from the dynamic tag’s controls. |
| Dynamic Tags | `dynamic-tags/index.md` | <img :src="$withBase('/assets/img/dynamic-tag-switcher.png')" alt="Dynamic Tag Switcher" style="float: right; width: 300px; margin-left: 20px; margin-bottom: 20px;"> |
| Remove Dynamic Tags | `dynamic-tags/remove-dynamic-tags.md` | To remove existing dynamic tag developers can simply unregister existing tags by passing the dynamic tag name. |
| Simple Example | `dynamic-tags/simple-example.md` | To put it all together, we're going to create a simple dynamic tag which will return a random number. To simplify the example, this dynamic tag won't have controls. But you can enhance the code and add two controls for minimum and maximum limits. |

## editor (11 docs)

| Standard | Path | Summary |
|---|---|---|
| Default Panel | `editor/default-panel.md` | By default, Elementor displays the [widgets panel](./widgets-panel/) when the editor is loaded for the first time. You can change this. |
| Elementor Panel | `editor/elementor-panel.md` | The panel is like an editing dashboard. This is the area where users can control all aspects of a page. It includes the global settings, page settings, widgets panel etc. |
| Elementor Preview | `editor/elementor-preview.md` | Preview is the area that displays a live preview of the page currently being edited. It is rendered by a JavaScript engine, typically without loading from the server side. In other words, this is the area where you can see what the site will look like. |
| Elementor Tabs | `editor/elementor-tabs.md` | <img :src="$withBase('/assets/img/elementor-tabs.png')" alt="Elementor Tabs" style="float: right; width: 300px; margin-left: 20px; margin-bottom: 20px;"> |
| History Panel | `editor/history-panel.md` | <img :src="$withBase('/assets/img/history-panel.png')" alt="Elementor History Panel" style="float: right; width: 300px; margin-left: 20px; margin-bottom: 20px;"> |
| Elementor Editor | `editor/index.md` | The editor is the environment in which users create pages and control site settings. Editor is a general term that includes two main areas - the preview and the panel. Each of these areas contains inner areas which can be extended by 3rd party developers. |
| Menu Panel | `editor/menu-panel.md` | <img :src="$withBase('/assets/img/menu-panel.png')" alt="Elementor Menu Panel" style="float: right; width: 300px; margin-left: 20px; margin-bottom: 20px;"> |
| Page Settings Panel | `editor/page-settings-panel.md` | <img :src="$withBase('/assets/img/page-settings-panel.png')" alt="Elementor Page Settings Panel" style="float: right; width: 300px; margin-left: 20px; margin-bottom: 20px;"> |
| Site Settings Panel | `editor/site-settings-panel.md` | <img :src="$withBase('/assets/img/site-settings-panel.png')" alt="Elementor Site Settings Panel" style="float: right; width: 300px; margin-left: 20px; margin-bottom: 20px;"> |
| User Preferences Panel | `editor/user-preferences-panel.md` | <img :src="$withBase('/assets/img/user-preferences-panel.png')" alt="Elementor User Preferences Panel" style="float: right; width: 300px; margin-left: 20px; margin-bottom: 20px;"> |
| Widgets Panel | `editor/widgets-panel.md` | <img :src="$withBase('/assets/img/widgets-panel.png')" alt="Elementor Widgets Panel" style="float: right; width: 300px; margin-left: 20px; margin-bottom: 20px;"> |

## editor-controls (61 docs)

| Standard | Path | Summary |
|---|---|---|
| AI | `editor-controls/ai.md` | <img :src="$withBase('/assets/img/elementor-control-ai-button.png')" alt="Control AI Button" style="float: right;"> |
| Conditional Display | `editor-controls/conditional-display.md` | In some cases, you may need to display controls based on a user’s selection in a dependent control. For example, turning a switcher control on may trigger the display of other controls. The controls mechanism in the editor has a special conditional display functionality. Let's see how it is used. |
| Alert Control | `editor-controls/control-alert.md` | <img :src="$withBase('/assets/img/controls/control-alert.png')" alt="Alert Control" style="float: right;"> |
| Entrance Animation Control | `editor-controls/control-animation.md` | <img :src="$withBase('/assets/img/controls/control-animation.png')" alt="Entrance Animation Control" style="float: right;"> |
| Box Shadow Control | `editor-controls/control-box-shadow.md` | Elementor Box Shadow control displays an input fields for horizontal shadow, vertical shadow, shadow blur, shadow spread and shadow color. |
| Button Control | `editor-controls/control-button.md` | Elementor button control displays a button in the panel that can trigger an event. |
| Choose Control | `editor-controls/control-choose.md` | <img :src="$withBase('/assets/img/controls/control-choose.png')" alt="Choose Control" style="float: right;"> |
| Code Control | `editor-controls/control-code.md` | <img :src="$withBase('/assets/img/controls/control-code.png')" alt="Code Control" style="float: right;"> |
| Color Control | `editor-controls/control-color.md` | <img :src="$withBase('/assets/img/controls/control-color.png')" alt="Color Control" style="float: right;"> |
| Date Time Control | `editor-controls/control-date-time.md` | <img :src="$withBase('/assets/img/controls/control-date-time.png')" alt="Date Time Control" style="float: right;"> |
| Deprecated Notice Control | `editor-controls/control-deprecated-notice.md` | Elementor Deprecated Notice control displays a pre-formatted notice in the panel, warning that the widget is deprecated and should be replaced. |
| Dimensions Control | `editor-controls/control-dimensions.md` | <img :src="$withBase('/assets/img/controls/control-dimensions.png')" alt="Dimensions Control" style="float: right;"> |
| Divider Control | `editor-controls/control-divider.md` | Elementor divider control displays a separator between controls. |
| Exit Animation Control | `editor-controls/control-exit-animation.md` | <img :src="$withBase('/assets/img/controls/control-exit-animation.png')" alt="Exit Animation Control" style="float: right;"> |
| Font Control | `editor-controls/control-font.md` | <img :src="$withBase('/assets/img/controls/control-font.png')" alt="Font Control" style="float: right;"> |
| Gallery Control | `editor-controls/control-gallery.md` | <img :src="$withBase('/assets/img/controls/control-gallery.png')" alt="Gallery Control" style="float: right;"> |
| Heading Control | `editor-controls/control-heading.md` | Elementor heading control displays a text heading between controls in the panel. |
| Hidden Control | `editor-controls/control-hidden.md` | Elementor hidden control adds a hidden input field to the panel. It can be used to add data without a visual presentation in the panel. This means that Elementor users do not have access to this control. |
| Hover Animation Control | `editor-controls/control-hover-animation.md` | <img :src="$withBase('/assets/img/controls/control-hover-animation.png')" alt="Hover Animation Control" style="float: right;"> |
| Icon Control | `editor-controls/control-icon.md` | ::: danger DEPRECATED |
| Icons Control | `editor-controls/control-icons.md` | <img :src="$withBase('/assets/img/controls/control-icons.png')" alt="Icons Control" style="float: right;"> |
| Image Dimensions Control | `editor-controls/control-image-dimensions.md` | <img :src="$withBase('/assets/img/controls/control-image-dimensions.png')" alt="Image Dimensions Control" style="float: right;"> |
| Media Control | `editor-controls/control-media.md` | <img :src="$withBase('/assets/img/controls/control-media.png')" alt="Media Control" style="float: right;"> |
| Notice Control | `editor-controls/control-notice.md` | <img :src="$withBase('/assets/img/controls/control-notice.png')" alt="Notice Control" style="float: right;"> |
| Number Control | `editor-controls/control-number.md` | <img :src="$withBase('/assets/img/controls/control-number.png')" alt="Number Control" style="float: right;"> |
| Popover Toggle Control | `editor-controls/control-popover-toggle.md` | <img :src="$withBase('/assets/img/controls/control-popover-toggle.png')" alt="Popover Toggle Control" style="float: right;"> |
| Control Popovers | `editor-controls/control-popovers.md` | Control popovers are UI wrappers used to group controls and display them in popups, which will appear over the panel. Using popovers can help you can declutter the panel by moving controls to popovers and displaying them only when the user chooses to see them. An excellent example of this is the typography control. It contains a toggle, and only if the user chooses to change the default typography settings will the extra controls appear in a popover. Popovers are created using two methods: `start_popover()` creates a new popover and `end_popover()` closes the popover. |
| Raw HTML Control | `editor-controls/control-raw-html.md` | Elementor raw HTML control displays an HTML content in the panel. |
| Repeater Control | `editor-controls/control-repeater.md` | <img :src="$withBase('/assets/img/controls/control-repeater.png')" alt="Repeater Control" style="float: right;"> |
| Control Section | `editor-controls/control-section.md` | <img :src="$withBase('/assets/img/controls/control-sections.png')" alt="Controls Section" style="float: right;"> |
| Select Control | `editor-controls/control-select.md` | <img :src="$withBase('/assets/img/controls/control-select.png')" alt="Select Control" style="float: right;"> |
| Select2 Control | `editor-controls/control-select2.md` | <img :src="$withBase('/assets/img/controls/control-select2.png')" alt="Select2 Control" style="float: right;"> |
| Slider Control | `editor-controls/control-slider.md` | <img :src="$withBase('/assets/img/controls/control-slider.png')" alt="Slider Control" style="float: right;"> |
| Switcher Control | `editor-controls/control-switcher.md` | <img :src="$withBase('/assets/img/controls/control-switcher.png')" alt="Switcher Control" style="float: right;"> |
| Control Tabs | `editor-controls/control-tabs.md` | <img :src="$withBase('/assets/img/controls/control-tabs.png')" alt="Control Tabs" style="float: right;"> |
| Text Shadow Control | `editor-controls/control-text-shadow.md` | Elementor Text Shadow control displays an input fields for horizontal shadow, vertical shadow, shadow blur and shadow color. |
| Text Control | `editor-controls/control-text.md` | <img :src="$withBase('/assets/img/controls/control-text.png')" alt="Text Control" style="float: right;"> |
| Textarea Control | `editor-controls/control-textarea.md` | <img :src="$withBase('/assets/img/controls/control-textarea.png')" alt="Textarea Control" style="float: right;"> |
| Control Types | `editor-controls/control-types.md` | Elementor includes a wide array of controls out-of-the-box. Each control has a custom template and optional default settings, default values, and other methods that affect the output of the control in the panel. |
| URL Control | `editor-controls/control-url.md` | <img :src="$withBase('/assets/img/controls/control-url.png')" alt="URL Control" style="float: right;"> |
| Visual Choice Control | `editor-controls/control-visual-choice.md` | <img :src="$withBase('/assets/img/controls/control-visual-choice.png')" alt="Visual Choice Control" style="float: right;"> |
| WYSIWYG Control | `editor-controls/control-wysiwyg.md` | <img :src="$withBase('/assets/img/controls/control-wysiwyg.png')" alt="WYSIWYG Control" style="float: right;"> |
| Dynamic Content | `editor-controls/dynamic-content.md` | Elementor can replace control outputs using [dynamic tags](../dynamic-tags/) to generate content programmatically. Dynamic capabilities turn static controls into smart components. This helps users add customized data from various sources to their site. Let's see how to set this up. |
| Frontend Available | `editor-controls/frontend-available.md` | In some cases, developers need to use the control value inside the widget JS loaded in the frontend. For example, an Elementor widget that uses an external slider library needs to get the amount of slides to display and pass the data to the library script in the frontend. Elementor lets developers expose control values to be used in the frontend. |
| Global Style | `editor-controls/global-style.md` | Elementor end-users can set global styles using the [site settings panel](../editor/site-settings-panel/). The control mechanism in the editor has a special functionality that allows these users to set custom styling, or inherit global styles. Let's see how to set it up. |
| Background Group Control | `editor-controls/group-control-background.md` | Elementor background group control displays input fields to define the background including the background color, background image, background gradient or background video. |
| Border Group Control | `editor-controls/group-control-border.md` | Elementor border group control displays input fields to define the border including the border type, border width and border color. |
| Box Shadow Group Control | `editor-controls/group-control-box-shadow.md` | Elementor box shadow group control displays input fields to define the box shadow including the horizontal shadow, vertical shadow, shadow blur, shadow spread, shadow color and the position. |
| CSS Filter Group Control | `editor-controls/group-control-css-filter.md` | Elementor CSS filter group control displays sliders fields to define the values of different CSS filters including blur, brightens, contrast, saturation or hue. |
| Image Size Group Control | `editor-controls/group-control-image-size.md` | Elementor image size group control displays input fields to define one of the default image sizes (thumbnail, medium, medium_large, large) or custom image dimensions. |
| Text Shadow Group Control | `editor-controls/group-control-text-shadow.md` | Elementor text shadow group control displays input fields to define the text shadow including the horizontal shadow, vertical shadow, shadow blur and shadow color. |
| Text Stroke Group Control | `editor-controls/group-control-text-stroke.md` | Elementor text stroke group control displays input fields to define the text stroke including the horizontal stroke, vertical stroke, stroke blur and stroke color. |
| Typography Group Control | `editor-controls/group-control-typography.md` | Elementor typography group control displays input fields to define the content typography including font size, font family, font weight, text transform, font style, line height and letter spacing. |
| Group Control | `editor-controls/group-control.md` | Group Control is a set of [regular controls](./regular-control/) and [responsive controls](./responsive-control/) with similar functionality, which are grouped together into a single control (e.g. typography control, text shadow control, box shadow control). To add group controls we use the `add_group_control()` method. |
| Elementor Editor Controls | `editor-controls/index.md` | Elementor Editor Controls are **input fields** and **UI elements** that are used to construct an interface. Controls allow users to customize available panel settings and change the design in the preview. |
| Labels and Description | `editor-controls/labels-description.md` | Controls are simply input fields where users fill the data. Each control can have a label that appears above the field and a short description appears below the field. The control mechanism in the editor has special arguments that help developers set those fields and style them. |
| Regular Control | `editor-controls/regular-control.md` | Regular controls are the basic building blocks that allow users to set different values for different types of input fields (text, number, color, image, icon, etc.). Regular controls are added using the `add_control()` method. |
| Responsive Control | `editor-controls/responsive-control.md` | Responsive controls are basically [regular controls](./regular-control/) with special capabilities that let users set different values for different devices and screen sizes. To add responsive controls we use the `add_responsive_control()` method. |
| Selectors Dictionary | `editor-controls/selectors-dictionary.md` | In some cases, you may need to update the values of a specific control. But, doing this might break existing sites which store the old values in the database. For these cases, Elementor offers a dictionary that helps developers transform old values into new values before using them in the code. |
| CSS Selectors | `editor-controls/selectors.md` | To transform control values to CSS styles, Elementor uses the `selector` argument for group controls and the `selectors` argument for other controls. These two arguments define which CSS selectors are used and on which CSS properties the values are set. Let's see how it works. |
| Using Controls | `editor-controls/using-controls.md` | Controls can be used inside Elementor widgets or Elementor panels. Controls used by end users to select their data. This data is saved in the database and later used to generate custom output based on the user's selection. |

## finder (9 docs)

| Standard | Path | Summary |
|---|---|---|
| Add Items to an Existing Category | `finder/add-items-to-existing-category.md` | In some cases, developers would like to add new items to existing finder categories. You can do that using the `elementor/finder/categories` filter hook. |
| Add New Finder Items | `finder/add-new-finder-items.md` | For each new item (link) we add to the finder, we need to define several fields. This includes the label, the URL, the icon, etc. All these links are grouped together in an array and returned together. |
| Advanced Example | `finder/advanced-example.md` | For a more advanced use-case, we'll replace static links with core WordPress functions, linking to the WordPress dashboard settings panels. |
| Finder Categories | `finder/finder-categories.md` | The finder returns a set of links organized by categories. Each category includes links to different sections on the site. For each search term entered by the user, the finder filters the list of links based on the relevant "keywords." |
| Finder Structure | `finder/finder-structure.md` | The finder is organized into categories, each of which includes an array of links. |
| Elementor Finder | `finder/index.md` | The finder component opens a popup search bar offering easy access to many pages and settings on the site. It can be used to create new posts, edit other pages, navigate to different setting pages, and more. |
| Remove Finder Categories | `finder/remove-finder-categories.md` | Developers can use the `elementor/finder/categories` filter hook to remove entire finder categories, along with all their items. |
| Remove Finder Items | `finder/remove-finder-items.md` | Developers can remove specific items from finder categories by using the `elementor/finder/categories` filter hook. |
| Simple Example | `finder/simple-example.md` | To see how easy it is to extend the finder, we are going to create a very simple finder category with static links to social media websites. |

## form-actions (9 docs)

| Standard | Path | Summary |
|---|---|---|
| Action Controls | `form-actions/action-controls.md` | Each action can incorporate [controls](./../editor-controls/) (setting fields), that allow users to select their data. When a user selects an action with these controls the control will be activated. Data entered into those fields is saved in the database and later used when [triggering the action](./action-run/). |
| Action Data | `form-actions/action-data.md` | Every action has basic information such as the unique action ID and label. This data is used in the code and displayed to the user in the editor. |
| Action On Export | `form-actions/action-on-export.md` | Best practice is to exclude action settings when exporting Elementor data. If your form action adds some settings ([action controls](./action-controls/)), you should not export them. |
| Action Run | `form-actions/action-run.md` | The actual method that executes the action when a form is submitted. This is the main method the action triggers. It can use optional data from custom controls, but that is not required. |
| Action Structure | `form-actions/action-structure.md` | Creating custom form actions, triggered after a form's submission, is not as hard as it sounds. |
| Add New Action | `form-actions/add-new-action.md` | The form widget has several built-in actions, but external developers can create and register new form actions. |
| Advanced Example | `form-actions/advanced-example.md` | For a more advanced example we are going to create an addon which will add a new subscriber to a [Sendy](https://sendy.co/) server using its [API](https://sendy.co/api). |
| Elementor Form Actions | `form-actions/index.md` | Form actions are tasks taken after a visitor has submitted data. An action can send the form data by email, redirect it to a different page, or send the data to an external marketing service - the possibilities are endless. |
| Simple Example | `form-actions/simple-example.md` | To demonstrate how easy it is to create new form actions, we're going to create an addon which will ping an external server. |

## form-fields (12 docs)

| Standard | Path | Summary |
|---|---|---|
| Add New Field | `form-fields/add-new-field.md` | The Form widget has built-in field types, but it also accepts new fields registered by external developers. |
| Advanced Example | `form-fields/advanced-example.md` | For a more advanced example we are going to create an addon with a credit card field. |
| Field Content Template | `form-fields/field-content-template.md` | When [rendering widgets](./../widgets/widget-rendering/) we have a PHP template and a JS template. However, [form field rendering](./field-render/) only has the PHP template, without the JS template. External developers can use a workaround to overcome this barrier. |
| Field Controls | `form-fields/field-controls.md` | Form fields can have additional controls where users can customize the form field. When the field is added to the form, those controls will be displayed in the field setting. The data entered into those controls is saved in the database and later can be used to render the field output or validate the field value. |
| Field Data | `form-fields/field-data.md` | Every field has basic information such as the field unique ID and the field label. This data is used in the code and displayed to the user in the editor. |
| Field Dependencies | `form-fields/field-dependencies.md` | Some form fields are dependent on custom scripts for functionality, and custom styles for look and feel. Let's see how to set field dependencies. |
| Field Render | `form-fields/field-render.md` | A field used in a form needs to have an output in the frontend. The render method sets the field's code when the field is displayed to the user on the site. |
| Field Structure | `form-fields/field-structure.md` | When creating new form fields we needs to have a few basic settings like a unique name and a label that will be used in the editor. Next is the render function that outputs the field markup. The field can also have a validation check. This last piece is an optional set of controls, where a user can configure their custom data. |
| Field Validation | `form-fields/field-validation.md` | Elementor offers the ability to run a series of checks to ensure that field data complies to a certain set of rules. The validating method checks if the field value is a valid value. |
| Elementor Form Fields | `form-fields/index.md` | The **Elementor Form widget** is an advanced, yet easy to use, tool to create web forms. This widget makes it easy to create and style any form using dozens of field types. |
| Remove Fields | `form-fields/remove-fields.md` | To remove an existing field from the form widget we simply need to delete it from the list of available fields. |
| Simple Example | `form-fields/simple-example.md` | To see how easy it is to extend the form widget, we are going to create an addon that removes the old `tel` field and adds a `local-tel` field. |

## getting-started (8 docs)

| Standard | Path | Summary |
|---|---|---|
| What is an Elementor addon? | `getting-started/addons.md` | Before you start planning and developing your Elementor addon, it’s important to understand what addons are and how they fit into Elementor. Addons are a way third party developers can extend the Elementor’s functionality, add new features, integrate external services, customize workflow and more. |
| Best Practices | `getting-started/best-practices.md` | This Best Practices guide is a living document for Elementor addon developers, meant to be revised as Elementor makes changes, introduces new features, and provides additional recommendations. We recommend following these best practices. |
| Elementor Components | `getting-started/components.md` | Elementor contains numerous components developers can modify to extend Elementor’s capabilities. This section contains a list of components currently covered by this documentation. |
| Creating Your First Addon | `getting-started/first-addon.md` | Let’s create a simple Elementor addon that adds two widgets to Elementor. The first will be a simple "Hello World" widget while the second will be similar, but with improved functionality. |
| What is Elementor? | `getting-started/index.md` | Elementor is the ultimate WordPress website builder that enables users to create pixel-perfect WordPress websites intuitively, professionally, and without having to write code. At the same time, it provides a framework allowing developers to extend its functionality providing users with additional features.  While it provides incredible ease-of-use, Elementor is also powerful and flexible, allowing creators to implement sophisticated designs and functionality, all within the Elementor framework. |
| Elementor Internals | `getting-started/internals.md` | Elementor has underlying technology, which we call the internals. In this section we’ll introduce you to the concepts you should understand when developing your Elementor addons. |
| Requirements | `getting-started/requirements.md` | Before starting to work, make sure you meet the requirements as outlined below. |
| The Docs Website | `getting-started/usage.md` | In order to further support and encourage the developer community, Elementor has created this updated and revised docs center where developers can access detailed documentation, clearly explaining how Elementor works and the options it provides developers. |

## hello-elementor-theme (14 docs)

| Standard | Path | Summary |
|---|---|---|
| Description Meta Tag | `hello-elementor-theme/hello_elementor_add_description_meta_tag.md` | To improve SEO without using external plugins, the theme adds a [meta tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) that contains the page/post excerpt. Developers can remove this meta tag by using a simple hook. |
| Register Theme Features | `hello-elementor-theme/hello_elementor_add_theme_support.md` | The theme registers various WordPress theme features. Developers can override this using a filter hook in a child-theme. |
| Register WooCommerce Features | `hello-elementor-theme/hello_elementor_add_woocommerce_support.md` | The theme registers various [WooCommerce theme features](https://woocommerce.com/document/woocommerce-theme-developer-handbook/). Developers can override this using a filter hook in a child-theme. |
| Content Width | `hello-elementor-theme/hello_elementor_content_width.md` | The theme sets content width of 800 pixels. Developers can override this using a filter hook in a child-theme. |
| Enable Skip Link | `hello-elementor-theme/hello_elementor_enable_skip_link.md` | The theme has a "Skip to content" link at the top of the page, it's used by screen readers to quickly navigate to the main content area. Developers can disable the skip link using a filter hook in a child-theme. |
| Enqueue Styles | `hello-elementor-theme/hello_elementor_enqueue_style.md` | The theme loads the `style.min.css` file by default. Developers can override this using a filter hook in a child-theme. |
| Enqueue Theme Styles | `hello-elementor-theme/hello_elementor_enqueue_theme_style.md` | The theme loads the `theme.min.css` file by default. Developers can override this using a filter hook in a child-theme. |
| Page Title | `hello-elementor-theme/hello_elementor_page_title.md` | The theme displays the `<h1>` page title above the content area. Developers can override this using a filter hook in a child-theme. This is useful when using page builders to style the entire page, titles included. |
| Register Post Type Features | `hello-elementor-theme/hello_elementor_post_type_support.md` | The theme registers a single post-type feature that adds excerpts to page. Developers can override this using a filter hook in a child-theme. |
| Register Elementor Theme Locations | `hello-elementor-theme/hello_elementor_register_elementor_locations.md` | The theme registers [Elementor theme locations](./../themes/). Developers can override this using a filter hook in a child-theme. |
| Register Navigation Menus | `hello-elementor-theme/hello_elementor_register_menus.md` | The theme registers two WordPress navigation menus, one for the header and the other footer. Developers can override this using a filter hook in a child-theme. |
| Skip Link URL | `hello-elementor-theme/hello_elementor_skip_link_url.md` | The theme has a "Skip to content" link at the top of the page, it's used by screen readers to quickly navigate to the main content area. Developers can modify the skip link URL using a filter hook in a child-theme. |
| Viewport Content | `hello-elementor-theme/hello_elementor_viewport_content.md` | The theme has a [viewport meta tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag), in the head, that controls the viewport's size and shape. Developers can modify the content attribute of the meta tag using a filter hook in a child-theme. |
| Hello Elementor Theme | `hello-elementor-theme/index.md` | Hello Elementor Theme is a lightweight and minimalist WordPress theme that was built to work with the Elementor page builder plugin. The theme has several features developers can control using WordPress hooks. |

## hooks (22 docs)

| Standard | Path | Summary |
|---|---|---|
| Custom Query Filter | `hooks/custom-query-filter.md` | Both **posts widgets** and **portfolio widgets** come with a robust query control that lets you select specific posts to show in the widget. But sometimes, you need more control over the query. For those situations, there is the custom query filter, which exposes the [WP_Query](https://developer.wordpress.org/reference/classes/wp_query/) object and allows you to customize the query in any way you want. |
| Elementor Init | `hooks/elementor-init.md` | Elementor has a hook that fires when a plugin is fully loaded. |
| Elementor Loaded | `hooks/elementor-loaded.md` | Elementor has a hook that fires when a plugin is loaded, before loading all the components. |
| Font Display | `hooks/font-display.md` | Elementor offers a filter hook that lets developers overwrite the "Custom Fonts" `font-display` value. In other words, you can control how font files are loaded and displayed by the browser. |
| Form Validation | `hooks/form-validation.md` | Form validation allows you to run a series of checks to ensure the data complies to certain rules. Elementor Pro provides a set of tools for validating data sent through the form widget. |
| Elementor Forms | `hooks/forms.md` | ::: danger |
| Frontend Content | `hooks/frontend-content.md` | Elementor has a hook that filters frontend content. It is applied to the final HTML content, i.e., all the content Elementor displays on the page/post. Developers can change the HTML output before Elementor displays it to the end-user. |
| Elementor Hooks | `hooks/index.md` | Elementor has many interesting hooks that let developers change default settings and even extend Elementor with new functionality. |
| Injecting Controls | `hooks/injecting-controls.md` | Elementor offers a set of special hooks that allow developers to inject new controls programmatically into many kinds of elements. You can inject new controls into all the elements, into specific elements, into the Elementor default widgets, and into widgets developed by other addon developers. |
| JS Hooks | `hooks/js.md` | Elementor has a number of JS hooks that allow developers to change default behavior and even add new functionality. |
| Mask Shapes | `hooks/masks.md` | Elementor offers the ability to apply overlay [masks](https://elementor.com/help/mask-option/) that create stylish designs for any element. By default Elementor offers a set of predefined masks. Additional masks can be added using a dedicated filter hook. |
| Parse Element CSS | `hooks/parse-element-css.md` | Elementor has a hook that lets developers add new CSS rules to the element before the CSS file is generated. |
| PHP Hooks | `hooks/php.md` | Elementor's PHP hooks, both filter hooks and action hooks. |
| Placeholder Image | `hooks/placeholder-image.md` | <img :src="$withBase('/assets/img/elementor-placeholder-image.png')" alt="Elementor Placeholder Image" style="float: right; width: 300px; margin-left: 20px; margin-bottom: 20px;"> |
| Print Google Fonts | `hooks/print-google-fonts.md` | Elementor offers a special filter hook that lets developers prevent Google fonts from loading. In other words, not all frontend Google fonts will be enqueued. |
| Print Widget Template | `hooks/print-widget-template.md` | Elementor has a hook that lets developers change a widget's JavaScript template in the [preview](./../editor/elementor-preview/) area. |
| Render Frontend Elements | `hooks/render-frontend-elements.md` | Elementor has a hook that lets developers add code before or after elements in the frontend. This hook can be applied to either a single element or all the elements on a page and is applied to the final HTML output of the element(s).  Developers can use this hook to change the HTML output before Elementor displays it to the end-user. |
| Render Widget Content | `hooks/render-widget-content.md` | Elementor has a hook that lets developers change a widget's content in the frontend. These changes will be applied to the final HTML content of the widget. In the preview area, they will be shown after the user finishes editing the element. |
| Save Editor Data | `hooks/save-editor-data.md` | Elementor has a hook that lets developers run code after the user has saved data in the editor. |
| Shape Dividers | `hooks/shapes.md` | Elementor offers the ability to add graphic [shape dividers](https://elementor.com/help/shape-divider/) that separate the sections of a page. By default Elementor offers a set of predefined dividers. Additional shape dividers can be added using a dedicated filter hook. |
| Widget Categories | `hooks/widget-categories.md` | Elementor **Widget Categories** are used to organize the widgets into groups. When Elementor is initialized, it registers several default categories. The categories are displayed in the widgets panel, only if they have widgets assigned to them. |
| Widget Skins | `hooks/widget-skins.md` | Elementor has a hook that lets developers apply custom skins to widgets. It runs after the widget constructor and registers custom skins for a specific widget types that support skins. |

## hosting (4 docs)

| Standard | Path | Summary |
|---|---|---|
| Elementor Hosting | `hosting/index.md` | Elementor hosting is an end-to-end solution gives you everything you need in one place: WordPress Managed Hosting, Elementor & Elementor Pro, Theme and Premium support, all tailored together to provide a seamless building experience and top performing websites. |
| Dynamic Page Cache | `hosting/page-cache-allow-page-cache.md` | Elementor hosting offers the option to control whether a page should be cached or not, depending on its dynamic nature. By using this hook, you can prevent caching of certain pages that require real-time or dynamic content updates, ensuring that the visitors always see the latest content on those pages. |
| Cache Changed URLs | `hosting/page-cache-changed-urls.md` | Elementor hosting offers the option to add custom co-changing URLs to the page cache whenever a specific content type (post, comment, WooCommerce product etc.) is updated. This can be useful for keeping cache up-to-date for pages that depend on the updated content. |
| Purge Everything | `hosting/page-cache-purge-everything.md` | Elementor hosting offers the option to purge the entire site cache, clearing all the CDN cache for the whole domain. Please note that it might take some time for this to take effect. |

## index.md (1 docs)

| Standard | Path | Summary |
|---|---|---|
| Index | `index.md` | --- |

## js (3 docs)

| Standard | Path | Summary |
|---|---|---|
| API --  `$e.commands` | `js/commands.md` | The new Commands API (since 2.7.0), provides a simple and convenient way to run something in the editor, create a widget, as well as show a notice or undo changes, using JS commands. |
| API - `$e.components` | `js/components.md` | The new Components API (since 2.7.0), provides a simple and convenient way to bind all route and commands, and keyboard shortcuts that belong to a UI component – into one controller. |
| API - `$e.hooks` | `js/hooks.md` | The `$e.hooks` api is a manager of `$e.hooks.ui` and `$e.hooks.data`. It allow you to create custom hooks. The hooks attached to `$e.commands` and each hook fired _after/before_ running a command, that runs by `$e.run()`. |

## managers (9 docs)

| Standard | Path | Summary |
|---|---|---|
| Elementor Managers | `managers/index.md` | Elementor is an extendable framework. It offers an architecture which allows external developers to add new functionality with addons. To do that, you need to create a new class for your component, which extends the base class and inherits its methods. You then need to register the class using the component manager, informing Elementor of its existence. |
| Registering Controls | `managers/registering-controls.md` | When you create new [Elementor controls](./../controls/) you must register them. This is done by hooking to the registration hook in the controls manager and passing a new control instance. |
| Registering Dynamic Tags | `managers/registering-dynamic-tags.md` | When you create new [dynamic tags](./../dynamic-tags/), you must register them. This is done by hooking to the registration hook in the dynamic tags manager and passing a new dynamic tag instance. |
| Registering Finder Categories | `managers/registering-finder-categories.md` | When you create new [finder categories](./../finder/) you must register them. This is done by hooking to the registration hook in the finder manager and passing a new finder category instance. |
| Registering Widgets | `managers/registering-widgets.md` | When you create new [Elementor widgets](./../widgets/), you must register them. This is done by hooking to the registration hook in the widgets manager and passing a new widget instance. |
| Unregistering Controls | `managers/unregistering-controls.md` | Developers can remove [Elementor controls](./../controls/) from the list of registered controls. This is done by hooking to the control manager and unregistering specific controls by passing the control ID. |
| Unregistering Dynamic Tags | `managers/unregistering-dynamic-tags.md` | Developers can remove [dynamic tags](./../dynamic-tags/) from the list of registered dynamic tags. This is done by hooking to the dynamic tags manager and unregistering specific dynamic tags by passing dynamic tag name. |
| Unregistering Finder Categories | `managers/unregistering-finder-categories.md` | Developers can remove [finder categories](./../finder/) from the list of registered categories. This is done by hooking to the finder categories manager and unregistering specific category by passing the category name. |
| Unregistering Widgets | `managers/unregistering-widgets.md` | Developers can remove [Elementor widgets](./../widgets/) from the list of registered widgets. This is done by hooking to the widget manager and unregistering specific widgets by passing the widget name. |

## scripts-styles (11 docs)

| Standard | Path | Summary |
|---|---|---|
| Control Scripts | `scripts-styles/control-scripts.md` | When you create new [Elementor controls](./../controls/) and need to register custom scripts, they must be registered using the [wp_register_script()](https://developer.wordpress.org/reference/functions/wp_register_script/) function and enqueued using the [wp_enqueue_script()](https://developer.wordpress.org/reference/functions/wp_enqueue_script/) function. To ensure that Elementor only loads the scripts in the editor, use the control `enqueue()` method. |
| Control Styles | `scripts-styles/control-styles.md` | When you create new [Elementor controls](./../controls/) and need to register custom stylesheets, they must be registered using the [wp_register_style()](https://developer.wordpress.org/reference/functions/wp_register_style/) function and enqueued using [wp_enqueue_style()](https://developer.wordpress.org/reference/functions/wp_enqueue_style/) function. To ensure that Elementor loads the stylesheets only in the editor, use the control `enqueue()` method. |
| Editor Scripts | `scripts-styles/editor-scripts.md` | When you develop addons that extend [Elementor Editor](./../editor/) and you have custom scripts, use `elementor/editor/before_enqueue_scripts` or `elementor/editor/after_enqueue_scripts` action hooks, which are fired when editor scripts are registered and enqueued. |
| Editor Styles | `scripts-styles/editor-styles.md` | When you develop addons that extend [Elementor Editor](./../editor/) and you have custom stylesheets, use `elementor/editor/before_enqueue_styles` or `elementor/editor/after_enqueue_scripts` action hooks, which are fired when editor styles are registered and enqueued. |
| Frontend Scripts | `scripts-styles/frontend-scripts.md` | Some addons have custom frontend scripts loaded on pages built with Elementor. Use `elementor/frontend/before_enqueue_scripts` or `elementor/frontend/after_enqueue_scripts` action hooks, which are fired when Elementor frontend scripts are registered and enqueued. |
| Frontend Styles | `scripts-styles/frontend-styles.md` | When using custom stylesheets, they must be registered to all pages using Elementor. Use the `elementor/frontend/before_enqueue_styles` or `elementor/frontend/after_enqueue_styles` action hooks, which are fired when Elementor frontend styles are registered and enqueued. |
| Scripts & Styles | `scripts-styles/index.md` | Just like WordPress, Elementor has special hooks to register custom scripts and styles. It's very important to use the correct hook in order to improve site performance. Using Elementor recommendations and best practices helps Elementor enqueue files dynamically only when they are used, reducing performance impact. |
| Preview Scripts | `scripts-styles/preview-scripts.md` | When you develop addons that extend [Elementor preview](./../editor/elementor-preview/) and need to register custom scripts, use the `elementor/preview/enqueue_scripts` action hook, which is fired when preview scripts are registered and enqueued. |
| Preview Styles | `scripts-styles/preview-styles.md` | When you develop addons that extend [Elementor preview](./../editor/elementor-preview/) and need to register custom stylesheets, use the `elementor/preview/enqueue_styles` action hook, which is fired when Elementor preview styles are registered and enqueued. |
| Widget Scripts | `scripts-styles/widget-scripts.md` | When you develop new [Elementor widgets](./../widgets/) and need to [register custom scripts](./../widgets/widget-dependencies/), they must be registered using the [wp_register_script()](https://developer.wordpress.org/reference/functions/wp_register_script/) function and set as dependencies using the widget `get_script_depends()` method. This way, Elementor will dynamically load these scripts only on pages using these widgets. |
| Widget Styles | `scripts-styles/widget-styles.md` | When you develop new [Elementor widgets](./../widgets/) and need to [register custom stylesheets](./../widgets/widget-dependencies/), they must be registered using the [wp_register_style()](https://developer.wordpress.org/reference/functions/wp_register_style/) function and set as dependencies using the widget `get_style_depends()` method. This way, Elementor will dynamically load these stylesheets only on pages using these widgets. |

## theme-conditions (9 docs)

| Standard | Path | Summary |
|---|---|---|
| Add New Condition | `theme-conditions/add-new-condition.md` | Elementor's template display mechanism has several built-in conditions, but external developers can create and register their own conditions. |
| Advanced Example | `theme-conditions/advanced-example.md` | For a more advanced use-case, we're going to create an addon that registers conditions based on the role of a logged-in visitor. The addon will help Elementor users to display some templates only to visitors with specific roles. |
| Condition Check | `theme-conditions/condition-check.md` | Elementor runs a series of checks to ensure that conditions comply with a certain set of rules. The `check()` method sets these checks. |
| Condition Data | `theme-conditions/condition-data.md` | Every condition has basic information such as the condition unique ID and the condition label. This data is used in the code and displayed to the user in the editor. |
| Condition Group Type | `theme-conditions/condition-group-type.md` | Conditions are grouped by type. There are several pre-defined types to choose from, based on the [WordPress Template Hierarchy](https://wphierarchy.com/). When creating a new condition, we have to assign the condition to a specific type. |
| Condition Structure | `theme-conditions/condition-structure.md` | Each condition needs to have a few basic settings, such as a unique name and label. In addition, a condition should be assigned to a group. A condition could have sub-conditions. The final, and most important, is the check method that checks whether the condition complies with a set of predefined rules. |
| Theme Conditions | `theme-conditions/index.md` | **Elementor Pro 2.0** introduced a condition-based template display mechanism. This allows users to specify under what conditions a template will be displayed. The conditions built into the mechanism cover most of the native *WordPress Template Hierarchy*, but sometimes you need more control with more specific conditions. |
| Simple Example | `theme-conditions/simple-example.md` | To demonstrate how easy it is to extend theme conditions, we're going to create an addon that registers a condition which will check to see if a visitor is logged-in. This addon will help Elementor users display some templates to logged-in visitors and other templates to anonymous visitors. |
| Sub-Conditions | `theme-conditions/sub-conditions.md` | Conditions can have sub-conditions in order to narrow the conditions. For example, instead of applying a condition to all `Singular` pages, applying it only to `Posts`, or a specific post. Sub-conditions help the user focus the main condition. |

## themes (7 docs)

| Standard | Path | Summary |
|---|---|---|
| Displaying Locations | `themes/displaying-locations.md` | Displaying Elementor locations in your theme is a simple process. The `elementor_theme_do_location()` function will display the location as defined by the user. In addition, theme developers can set fallback designs if a template was assigned to the location. |
| Theme Locations | `themes/index.md` | **Elementor Pro 2.0** introduced a **theme builder**. This feature transformed Elementor from a *page-builder* to a full *site-builder*. |
| Migrating Themes with Functions | `themes/migrating-themes-with-functions.md` | In this example, we'll add theme locations to the [original theme](./original-theme/) using simple **functions**. After migration, the theme will look as follows: |
| Migrating Themes with Hooks | `themes/migrating-themes-with-hooks.md` | In this example, we'll add theme locations to the [original theme](./original-theme/) using **hooks**. After migration, the theme will look as follows: |
| Migrating Themes | `themes/migrating-themes.md` | Now we'll see how to support Elementor theme locations in your theme. The logic behind the process is simple, you just need to wrap your code with an Elementor function/hook that checks to see if the user prefers using the Elementor template or the original theme design. |
| Original Theme | `themes/original-theme.md` | To simplify the theme migration process, we stripped all custom code from the original theme (including the WordPress loop), and moved it to the `/template-parts/` folder. This way the code snippets will be much shorter and simpler to understand. |
| Registering Locations | `themes/registering-locations.md` | To support Elementor locations, the theme needs to register supported locations in the `functions.php` file. Theme developers can support all core locations, some locations or create new locations. |

## widgets (23 docs)

| Standard | Path | Summary |
|---|---|---|
| Add New Widget | `widgets/add-new-widget.md` | Elementor offers many built-in widgets out of the box, but it also allows external developers to register new widgets. |
| Advanced Example | `widgets/advanced-example.md` | For a more advanced example we will create a widget with a repeater field, to allow the user to generate a list with items. It will also have a conditional field display when choosing "other" marker type, to display a new control that let's the user enter a [custom marker](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker). |
| Elementor Widgets | `widgets/index.md` | Elementor is packed with dozens of useful widgets in the **widgets panel**. These widgets are divided into categories. Each widget has a set of custom controls (input fields) allowing end-users to enter data. |
| Remove Widgets | `widgets/remove-widgets.md` | To remove existing widget developers can simply unregister existing widget by passing the widget name. |
| Rendering HTML Attributes | `widgets/rendering-html-attribute.md` | This type of rendering is used to add render attributes to specific HTML elements. For example, a widget can add a new `<div>` tag with a hardcoded "class" attribute or add a new `<a>` tag with hardcoded "target" and "rel" attributes. When used, you need to add `if` statements to check whether or not there are classes/target/rel attributed before adding them to the HTML tag. In addition, you need to escape user data with `esc_attr()` to improve security. |
| Rendering Inline Editing | `widgets/rendering-inline-editing.md` | When developing widgets, developers can define which controls will be inline editable in both the editor panel and preview area. |
| Rendering Media | `widgets/rendering-media.md` | Elementor lets you select an image using the media control defined in the `\Elementor\Control_Media` class. There are two ways to render media files. |
| Rendering Repeaters | `widgets/rendering-repeaters.md` | One advanced use case is to render multiple elements using the repeater control. Here, users set multiple fields in the repeater control and we need to print them on screen. |
| Rendering Style | `widgets/rendering-style.md` | A common [widget rendering](./widget-rendering/) use case is using the control value to style different HTML elements. Usually used by controls from the content tab. |
| Rendering Text | `widgets/rendering-text.md` | The most common [widget rendering](./widget-rendering/) use case is to print the value of a simple text control. These controls are usually found in the content tab. |
| Simple Example | `widgets/simple-example.md` | Putting all these pieces together, we're going to create a simple Elementor widget which will use the [native oEmbed functionality](https://developer.wordpress.org/reference/functions/wp_oembed_get/) of WordPress to auto-embed content from external sites using simple URLs. |
| Widget Categories | `widgets/widget-categories.md` | <img :src="$withBase('/assets/img/elementor-categories.png')" alt="Elementor Widget Categories" style="float: right; width: 300px; margin-left: 20px; margin-bottom: 20px;"> |
| Widget Controls | `widgets/widget-controls.md` | Each widget needs to have some [controls](./../editor-controls/) (setting fields), where users can select their data. This data is saved in the database and later used to [generate custom output](./widget-rendering/) based on the user's selection. |
| Widget Data | `widgets/widget-data.md` | Every widget requires basic information such as the widget ID, label and icon. In addition, a widget can have optional data providing extra information like an external link describing how to use the widget or promotion to promote premium version of the widget. |
| Widget Dependencies | `widgets/widget-dependencies.md` | Some widgets are dependent on custom scripts for functionality and custom styles for look and feel. Widgets can use external JS libraries, CSS frameworks, or custom JS handlers. Let's see how to use them. |
| Widget Information | `widgets/widget-information.md` | Elementor widget need to have a unique ID used in the code, and an addition basic information used in the Elementor editor. |
| Widget DOM Optimization | `widgets/widget-inner-wrapper.md` | Elementor widgets define their own markup in the `render()` method. However, Elementor wraps each widget in two `<div>` elements; the outer `<div class="elementor-widget">` element, and the inner `<div class="elementor-widget-container">` element. In the past, these additional wrappers allow Elementor to add additional styles and features. |
| Widget Optimization | `widgets/widget-optimization.md` | Elementor provides various methods to optimize widgets and enhance performance. To maintain backward compatibility, not all optimizations are applied to every widget. Additionally, each widget has unique characteristics, so certain optimizations may not be applicable in all cases. |
| Widget Output Caching | `widgets/widget-output-caching.md` | Elementor offers a feature to minimize the impact of widgets on page performance. For widgets that generate static output, Elementor can cache the HTML, avoiding the need to render it each time the page loads. |
| Widget Promotions | `widgets/widget-promotions.md` | <img :src="$withBase('/assets/img/elementor-widget-promotion.png')" alt="Elementor Widget Promotion" style="float: right; width: 300px; margin-left: 20px; margin-bottom: 20px;"> |
| Widget Rendering | `widgets/widget-rendering.md` | The last step in widget development is to display the output. Each widget needs to render the data returned from the controls, and generate the final HTML displayed in the frontend and the preview area. |
| Widget Settings | `widgets/widget-settings.md` | Before the [widget rendering](./widget-rendering/) function starts generating the final HTML output, it needs to retrieve data from the controls. |
| Widget Structure | `widgets/widget-structure.md` | Creating a custom Elementor Widget is not very different from creating a native WordPress widget. Start by creating a class that extends the `\Elementor\Widget_Base` class and fill in all the required methods. |
