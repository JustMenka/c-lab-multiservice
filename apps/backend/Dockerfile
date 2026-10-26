FROM gcc:13-bookworm AS builder

WORKDIR /app

COPY . .

RUN make clean && make

RUN make -C lib && make -C apps/backend

FROM debian:bookworm-slim

WORKDIR /app

COPY --from=builder /app/apps/backend/backend ./backend

EXPOSE 9000

CMD ["./backend"]
