# Reflection

## a. What is amqp?

AMQP (Advanced Message Queuing Protocol) adalah protokol komunikasi standar terbuka yang digunakan pada message-oriented middleware. AMQP memungkinkan aplikasi atau service saling berkomunikasi dengan cara mengirim pesan melalui message broker seperti RabbitMQ. Dengan AMQP, sistem dapat bertukar data secara asynchronous sehingga aplikasi menjadi lebih reliable, scalable, dan tidak saling bergantung secara langsung.

## b. What does it mean? `guest:guest@localhost:5672` , what is the first guest, and what is the second guest, and what is localhost:5672 is for?


`guest:guest@localhost:5672` adalah alamat koneksi RabbitMQ yang digunakan pada program Rust.

Format:

```text
username:password@host:port
```

Jadi:

```text
guest:guest@localhost:5672
```

berarti:

- `guest` pertama = username RabbitMQ
- `guest` kedua = password RabbitMQ
- `localhost` = RabbitMQ berjalan di komputer sendiri/local
- `5672` = port default AMQP RabbitMQ

Berdasarkan kode Rust berikut:

```rust
CrosstownBus::new_queue_listener(
    "amqp://guest:guest@localhost:5672".to_owned()
)
```

program akan terhubung ke RabbitMQ yang berjalan di komputer lokal menggunakan username `guest` dan password `guest` melalui port `5672`.