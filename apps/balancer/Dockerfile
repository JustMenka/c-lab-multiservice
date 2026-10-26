FROM gcc:13-bookworm AS builder

WORKDIR /app

COPY . .

RUN make clean && make -C lib && make -C apps/balancer

FROM debian:bookworm-slim

WORKDIR /app

COPY --from=builder /app/apps/balancer/balancer ./balancer

EXPOSE 8080

CMD ["./balancer"]
