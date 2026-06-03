# ĐỀ 32 — API GRAPHQL CƠ BẢN

## Phần A — Đọc và giải thích code
Cho đoạn mã sau:

```js
const { ApolloServer, gql } = require("apollo-server");

const typeDefs = gql`
  type User {
    id: ID!
    name: String!
  }

  type Query {
    users: [User!]!
  }
`;

const resolvers = {
    Query: {
        users: () => [{ id: "1", name: "An" }]
    }
};

new ApolloServer({ typeDefs, resolvers }).listen(4000);
```

### Yêu cầu
- Giải thích đoạn code đang làm gì.
- Giải thích vai trò của `typeDefs`, `resolvers`, `Query`, `ID`, và `String!`.

## Phần B — Sửa hoặc viết bổ sung
Sửa code để:
- thêm query `user(id: ID!): User`,
- trả `null` nếu không tìm thấy user,
- thêm mutation `createUser(name: String!): User`,
- kiểm tra `name` không được rỗng.

## Phần C — Câu hỏi vấn đáp
1. GraphQL khác REST như thế nào?
2. Resolver trong GraphQL dùng để làm gì?
3. Vì sao GraphQL cần schema?
4. Nhược điểm của GraphQL là gì?

