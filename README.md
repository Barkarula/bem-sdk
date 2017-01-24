# bem-fs-scheme

[BEM file system](https://en.bem.info/method/filesystem/#principles-of-file-system-organization-for-bem-projects) [schemes](https://en.bem.info/faq/#why-create-separate-directories-and-files-for-every-block-and-technology).

## Supported schemes

* [nested](https://en.bem.info/methodology/filestructure/#nested)
* [flat](https://en.bem.info/methodology/filestructure/#flat)

## Usage
```js
var BemCell = require('@bem/cell'),
    BemEntityName = require('@bem/entity-name');

var atom = new BemCell(
    {
        entity: new BemEntityName({
            block: 'b1',
            elem: 'e1',
            mod: {name: 'm1', val: 'v1'}
        }),
        tech: 'js'
    }
);

var options = {
    naming: {
        elem: '__',
        mod: '-'
    }
}; // this is default value

var bemFs = require('bem-fs-scheme')('nested')

bemFs.path(atom, options); // b1/__e1/_m1/b1__e1_m1_v1.js
```

License
-------

Code and documentation © 2015 YANDEX LLC. Code released under the [Mozilla Public License 2.0](LICENSE.txt).
