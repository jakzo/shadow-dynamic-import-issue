# shadow-cljs dynamic import issue

```sh
# Compile without dynamic import (succeeds)
$ shadow-cljs compile normal

shadow-cljs - config: /.../shadow-dynamic-import-issue/shadow-cljs.edn  cli version: 2.7.17  node: v11.6.0
shadow-cljs - starting ...
[:normal] Compiling ...
[:normal] Build completed. (27 files, 0 compiled, 0 warnings, 1.40s)

# Compile with dynamic import (fails)
$ shadow-cljs compile dynamic

shadow-cljs - config: /.../shadow-dynamic-import-issue/shadow-cljs.edn  cli version: 2.7.17  node: v11.6.0
shadow-cljs - starting ...
[:dynamic] Compiling ...
errors in file: /.../shadow-dynamic-import-issue/node_modules/dynamic-import/index.js
{:js-str-offsets [], :js-esm false, :js-imports [], :js-invalid-requires [], :goog-provides [], :js-language "es3", :goog-module nil, :js-warnings [], :resource-name "node_modules/dynamic-import/index.js", :js-requires [], :js-errors [{:line 2, :column 2, :message "'}' expected"}], :goog-requires [], :tag :shadow.build.npm/errors, :uses-global-buffer false}
ExceptionInfo: errors in file: /.../shadow-dynamic-import-issue/node_modules/dynamic-import/index.js
        clojure.core/ex-info (core.clj:4739)
        clojure.core/ex-info (core.clj:4739)
        shadow.build.npm/get-file-info* (npm.clj:530)
        ...
```
