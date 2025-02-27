# File Browser Interface
## Variants
a) UI holds a recursive list of folders and caches new requests 

b) UI asks everytime if the user changes the path

## TS Interface

```
interface FilesystemFolder {
    name: string;
    path: string;
    children: boolean;
    child?: FilesystemFolder;
    probablyDataset?: boolean;
}
```

## Workflow

### Variant a)
```mermaid
sequenceDiagram
participant ui as Frontend
participant ig as Ingestor
participant fs as Filesystem

ui ->> ig: GET /datasets PARAM{path: "/", page: x, pageSize: y}
ig ->> fs: CHECK {path} permission
ig ->> fs: LS {path}
fs ->> ig: LS INFO {path}
ig ->> ui: RETURN {folders: [{name: string, path: string, children: boolean, probablyDataset: boolean}]}

ui ->> ig: GET /datasets PARAM{path: "/{path}", page: x, pageSize: y}
ig ->> fs: CHECK {path} permission
ig ->> fs: LS {path}
fs ->> ig: LS INFO {path}
ig ->> ui: RETURN {folders: [{name: string, path: string, children: boolean}]}
```

### Variant b)
In this case we need some kind of refresh button or a timeout to refresh the cache.

```mermaid
sequenceDiagram
participant ui as Frontend
participant ig as Ingestor
participant fs as Filesystem

ui ->> ui: Create igFileSystemCache = {}

ui ->> ig: GET /datasets PARAM{path: "/", page: x, pageSize: y}
ig ->> fs: CHECK {path} permission
ig ->> fs: LS {path}
fs ->> ig: LS INFO {path}
ig ->> ui: RETURN {folders: [{name: string, path: string, children: boolean, probablyDataset: boolean}]}

ui ->> ui: Add to igFileSystemCache

ui ->> ig: GET /datasets PARAM{path: "/{path}", page: x, pageSize: y}
ig ->> fs: CHECK {path} permission
ig ->> fs: LS {path}
fs ->> ig: LS INFO {path}
ig ->> ui: RETURN {folders: [{name: string, path: string, children: boolean}]}

ui ->> ui: Add to igFileSystemCache[path]
```