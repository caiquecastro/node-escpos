ESC/POS Printer driver for Node.js

```js
import escpos from '@escpos/printer';
import usb    from '@escpos/usb';

const adapter = new usb('/dev/usb0');
const printer = escpos(adapter, {
  profile: '..',
  encoding: '..',
});

const { align, text, image, cut } = printer;

(async () => {

  await align('center');
  await text('hello world');
  await image('/tmp/escpos.png');
  await cut();

})();
```
