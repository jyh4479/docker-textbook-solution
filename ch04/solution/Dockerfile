FROM diamol/golang AS builder

COPY main.go .
RUN go build -o /server
RUN chmod 777 /server

FROM diamol/base
CMD ["/server"]

COPY --from=builder /server /server
ENV USER=sixeyed
EXPOSE 80
COPY index.html /