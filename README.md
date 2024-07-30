# Service APIs
Protocol Buffers for service's

## Usage

### Generate clients with [buf](https://buf.build/):

Ensure [buf](https://buf.build/docs/installation) and [protoc](https://grpc.io/docs/protoc-installation/) are installed on your system.

```sh
buf dep update ./proto
```

#### Rust (tonic):

##### Dependencies:

Install "protoc-gen-\*" with cargo.

```sh
cargo install protoc-gen-prost
cargo install protoc-gen-prost-crate
cargo install protoc-gen-tonic
```

##### Generate:

```sh
buf generate proto --template proto/buf.gen.rust.yaml
```

#### Typescript in Browser:

##### Dependencies:

Install "protoc-gen-\*" with npm.

```sh
npm install -g ts-proto
```

##### Generate:

```sh
buf generate proto --template proto/buf.gen.ts.yaml
```

### Proto linter

#### Dependencies:

Install protolint with npx.

 ```sh
npx protolint
```

#### Lint:

 ```sh
protolint lint proto
```

Outputs will be in out/ directory.

### Developement Hints

When using "vscode-proto3" extention in VS Code, add the following to the '.vscode/settings.json' file in order to make the import paths work.

```json
{
  "protoc": {
    "options": ["--proto_path=proto"]
  }
}
```
