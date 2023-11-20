# Steps used to reproduce
Init simple ts project
```
yarn init -y
yarn add fastify && yarn add -D @types/node typescript
yarn run tsc --init
```
Change "target": "es2016" in tsconfig.json to "es2020" per https://fastify.dev/docs/latest/Reference/TypeScript/#getting-started
Create index.ts (from the getting started section in the above link)
```ts
import fastify from 'fastify'

const server = fastify()

server.get('/ping', async (request, reply) => {
  return 'pong\n'
})

server.listen({ port: 8080 }, (err, address) => {
  if (err) {
    console.error(err)
    process.exit(1)
  }
  console.log(`Server listening at ${address}`)
})
```