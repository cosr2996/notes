## Tiempos TTL de los distintos sistemas operativos más usados

![[1.png]]

A través del presente post, quiero reflejar los distintos valores TTLs que os podéis encontrar en los distintos sistemas operativos. Tal y como sabéis, el valor TTL nos indica el tiempo que se puede disponer de un paquete antes de descartarlo.

- Linux/Unix: 64
- Windows: 128
- MacOS: 64
- Solaris/AIX: 254
- FreeBSD: 64

Destacar al respecto que podréis encontrar cual es vuestro ttl ejecutando el siguiente comando:

```
ping -4 localhost
```

![[2.webp]]

Finalmente, indicar que si hacéis el ping a un equipo en vez de a vuestro sistema operativo, podréis conocer con el TTL que sistema operativo se ejecuta siempre y cuando responda a peticiones ICMP.