# frontend-slot-footer

This package provides a wrapped version of the footer using [Frontend Plugin Framework](https://github.com/openedx/frontend-plugin-framework).

### Slot ID: `footer_slot`

## Description

This slot is used to replace/modify/hide the footer.

## Example

The following `env.config.jsx` will replace the default footer.

![Screenshot of Default Footer](./docs/images/default_footer.png)

with a simple custom footer

![Screenshot of Custom Footer](./docs/images/custom_footer.png)

```js
import { DIRECT_PLUGIN, PLUGIN_OPERATIONS } from '@openedx/frontend-plugin-framework';

const config = {
  pluginSlots: {
    footer_slot: {
      plugins: [
        {
          // Hide the default footer
          op: PLUGIN_OPERATIONS.Hide,
          widgetId: 'default_contents',
        },
        {
          // Insert a custom footer
          op: PLUGIN_OPERATIONS.Insert,
          widget: {
            id: 'custom_footer',
            type: DIRECT_PLUGIN,
            RenderWidget: () => (
              <h1 style={{textAlign: 'center'}}>🦶</h1>
            ),
          },
        },
      ]
    }
  },
}

export default config;
```
