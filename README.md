# explore-gRPC

## How To Run
1. Jalankan command di bawah untuk meng-generate file:
- `helloworld_pb.js`: berisi kelas `HelloRequest` dan `HelloReply`
- `helloworld_grpc_web_js.js`: berisi kelas `GreeterClient`

```sh
$ protoc -I. helloworld.proto --js_out=import_style=commonjs:. --grpc-web_out=import_style=commonjs,mode=grpcwebtext:.
```

2. Compile kode client untuk dapat dikonsumsi oleh browser
```sh
$ npm install
$ npx webpack client.js
```

3. Jalankan NodeJS gRPC service. Servis ini mendengarkan port `:9090`.
```sh
$ node server.js &
```