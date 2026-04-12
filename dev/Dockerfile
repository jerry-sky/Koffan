FROM golang:1.25-alpine

WORKDIR /app

# Install build dependencies for SQLite
RUN apk add --no-cache gcc musl-dev

# Copy go mod files
COPY go.mod go.sum ./
RUN go mod download

RUN go install github.com/air-verse/air@latest

# Copy source code
COPY . .

# Read version and build with ldflags
ENTRYPOINT ["air"]

