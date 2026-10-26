FROM gcc:13-bookworm AS builder

WORKDIR /app

COPY . .

RUN make clean && make -C lib && make -C apps/loadgen

FROM debian:bookworm-slim

WORKDIR /app

COPY --from=builder /app/apps/loadgen/loadgen ./loadgen

CMD [ "./loadgen" ]