# fullcycle-grpc

Repositório com o conteúdo prático da aula de comunição entre serviços

# comandos iniciais

<!-- go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest -->
sudo apt install -y protobuf-compiler  
go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28  
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.2
go install github.com/ktr0731/evans@latest

<!-- Inicia projeto go -->
go mod init github.com/blsilva89/fullcycle-grpc  

<!-- Instala dependencias -->
go mod tidy  

<!-- Gera arquivos com base no proto -->
protoc --go_out=. --go-grpc_out=. proto/course_category.proto

<!-- Executa o servidor -->
go run cmd/grpcServer/main.go

<!-- Executa o client grpc -->
evans -r repl