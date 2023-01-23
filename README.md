# minimal-apis-auth-jwt-bearer-main
Este código é uma implementação de autenticação e autorização em uma aplicação ASP.NET Core usando o pacote Microsoft.AspNetCore.Authentication.JwtBearer e o MinimalApiAuth.

A primeira parte do código configura a validação do token JWT. Ele cria uma chave a partir de uma string secreta armazenada em um objeto Settings e a usa para configurar a validação do token. Ele também adiciona o esquema de autenticação JWTBearer como o esquema padrão de autenticação e desafio da aplicação.

Em seguida, o código adiciona regras de autorização para as políticas "Admin" e "Employee", exigindo respectivamente os papéis "manager" e "employee". Ele então habilita a autenticação e a autorização na aplicação.

O código também inclui várias rotas que são protegidas por autenticação e/ou autorização. A rota "/login" permite que um usuário forneça seu nome de usuário e senha para obter um token JWT de acesso. Se as credenciais fornecidas são válidas, o token é gerado e retornado ao usuário juntamente com as informações do usuário.

As rotas "/anonymous", "/authenticated", "/employee" e "/manager" são exemplos de rotas protegidas por diferentes níveis de autorização. A rota "/anonymous" não exige autenticação e pode ser acessada por qualquer usuário. A rota "/authenticated" exige autenticação, mas não exige nenhum papel específico. As rotas "/employee" e "/manager" exigem autenticação e respectivamente o papel "employee" e "manager".
