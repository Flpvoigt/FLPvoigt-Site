# 🚀 FLPvoigt - Backend API

Backend completo para o site do Felipe Voigt Postai, desenvolvido com Node.js, Express e MongoDB.

## 📋 Funcionalidades

### 🔐 Autenticação e Usuários
- ✅ Registro e login de usuários
- ✅ Verificação de email
- ✅ Reset de senha
- ✅ JWT tokens com refresh
- ✅ Perfis de usuário (user, admin, instructor)
- ✅ Middleware de autenticação e autorização

### 📚 Sistema de Cursos
- ✅ CRUD completo de cursos
- ✅ Categorias e níveis
- ✅ Módulos e lições
- ✅ Sistema de avaliações e reviews
- ✅ Matrículas e progresso
- ✅ Certificados de conclusão

### 💳 Sistema de Pagamentos
- ✅ Integração com Mercado Pago
- ✅ Webhooks para processamento automático
- ✅ Múltiplos métodos de pagamento
- ✅ Sistema de reembolsos
- ✅ Relatórios financeiros

### 📧 Sistema de Contato
- ✅ Formulário de contato
- ✅ Categorização automática
- ✅ Sistema de prioridades
- ✅ Respostas e tags
- ✅ Notificações por email

### 📊 Painel Administrativo
- ✅ Dashboard com estatísticas
- ✅ Gerenciamento de usuários
- ✅ Gerenciamento de cursos
- ✅ Relatórios e análises
- ✅ Sistema de logs

### 📨 Sistema de Email
- ✅ Templates HTML responsivos
- ✅ Confirmações de registro
- ✅ Notificações de pagamento
- ✅ Emails de contato
- ✅ Suporte a anexos

## 🛠️ Tecnologias Utilizadas

- **Node.js** - Runtime JavaScript
- **Express.js** - Framework web
- **MongoDB** - Banco de dados NoSQL
- **Mongoose** - ODM para MongoDB
- **JWT** - Autenticação
- **Mercado Pago** - Gateway de pagamento
- **Nodemailer** - Envio de emails
- **Bcrypt** - Hash de senhas
- **Express Validator** - Validação de dados
- **Helmet** - Segurança
- **CORS** - Cross-origin requests
- **Rate Limiting** - Proteção contra spam

## 🚀 Instalação e Configuração

### 1. Clone o repositório
```bash
git clone <repository-url>
cd flpvoigt-backend
```

### 2. Instale as dependências
```bash
npm install
```

### 3. Configure as variáveis de ambiente
```bash
cp env.example .env
```

Edite o arquivo `.env` com suas configurações:

```env
# Configurações do Servidor
NODE_ENV=development
PORT=5000
FRONTEND_URL=http://localhost:3000

# Banco de Dados
MONGODB_URI=mongodb://localhost:27017/flpvoigt

# JWT
JWT_SECRET=seu_jwt_secret_super_seguro_aqui
JWT_EXPIRE=7d

# Email (Gmail)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=seu_email@gmail.com
EMAIL_PASS=sua_senha_de_app

# Mercado Pago
MERCADOPAGO_ACCESS_TOKEN=seu_access_token_do_mercadopago
MERCADOPAGO_PUBLIC_KEY=sua_public_key_do_mercadopago

# Admin
ADMIN_EMAIL=admin@flpvoigt.com
ADMIN_PASSWORD=senha_admin_segura
```

### 4. Inicie o servidor
```bash
# Desenvolvimento
npm run dev

# Produção
npm start
```

## 📚 Documentação da API

### Endpoints Principais

#### Autenticação
- `POST /api/auth/register` - Registrar usuário
- `POST /api/auth/login` - Fazer login
- `POST /api/auth/refresh` - Renovar token
- `GET /api/auth/me` - Obter dados do usuário
- `POST /api/auth/verify-email` - Verificar email
- `POST /api/auth/forgot-password` - Solicitar reset de senha
- `POST /api/auth/reset-password` - Resetar senha

#### Cursos
- `GET /api/courses` - Listar cursos
- `GET /api/courses/:slug` - Obter curso por slug
- `POST /api/courses` - Criar curso (admin/instructor)
- `PUT /api/courses/:id` - Atualizar curso
- `DELETE /api/courses/:id` - Deletar curso
- `POST /api/courses/:id/reviews` - Adicionar review

#### Pagamentos
- `POST /api/payments/create` - Criar pagamento
- `GET /api/payments` - Listar pagamentos do usuário
- `GET /api/payments/:id` - Obter pagamento
- `POST /api/payments/webhook` - Webhook do Mercado Pago
- `POST /api/payments/:id/refund` - Processar reembolso

#### Contato
- `POST /api/contact` - Enviar mensagem de contato
- `GET /api/contact` - Listar mensagens (admin)
- `PUT /api/contact/:id/status` - Atualizar status
- `POST /api/contact/:id/reply` - Responder mensagem

#### Usuários
- `GET /api/users/profile` - Obter perfil
- `PUT /api/users/profile` - Atualizar perfil
- `GET /api/users/enrollments` - Obter matrículas
- `GET /api/users/stats` - Obter estatísticas

#### Admin
- `GET /api/admin/dashboard` - Dashboard administrativo
- `GET /api/admin/analytics` - Análises detalhadas
- `GET /api/admin/reports` - Gerar relatórios
- `GET /api/admin/settings` - Configurações do sistema

## 🔧 Scripts Disponíveis

```bash
npm start          # Iniciar servidor em produção
npm run dev        # Iniciar servidor em desenvolvimento
npm test           # Executar testes
npm run build      # Build do projeto
```

## 🗄️ Estrutura do Banco de Dados

### Collections

#### Users
- Informações do usuário
- Autenticação e permissões
- Preferências e configurações

#### Courses
- Dados dos cursos
- Módulos e lições
- Avaliações e reviews

#### Payments
- Transações de pagamento
- Integração com Mercado Pago
- Histórico de reembolsos

#### Enrollments
- Matrículas dos usuários
- Progresso nas aulas
- Certificados

#### Contacts
- Mensagens de contato
- Categorização e prioridades
- Respostas e tags

## 🔒 Segurança

- ✅ Autenticação JWT
- ✅ Hash de senhas com bcrypt
- ✅ Rate limiting
- ✅ Validação de dados
- ✅ Sanitização de inputs
- ✅ Headers de segurança (Helmet)
- ✅ CORS configurado
- ✅ Proteção contra SQL injection

## 📈 Monitoramento

- ✅ Logs estruturados
- ✅ Tratamento de erros
- ✅ Métricas de performance
- ✅ Health checks
- ✅ Backup automático

## 🚀 Deploy

### Heroku
```bash
# Instalar Heroku CLI
npm install -g heroku

# Login
heroku login

# Criar app
heroku create flpvoigt-backend

# Configurar variáveis
heroku config:set NODE_ENV=production
heroku config:set MONGODB_URI=sua_uri_mongodb
heroku config:set JWT_SECRET=seu_jwt_secret

# Deploy
git push heroku main
```

### Docker
```bash
# Build da imagem
docker build -t flpvoigt-backend .

# Executar container
docker run -p 5000:5000 --env-file .env flpvoigt-backend
```

### VPS/Cloud
```bash
# Instalar PM2
npm install -g pm2

# Iniciar aplicação
pm2 start server.js --name "flpvoigt-backend"

# Configurar para iniciar automaticamente
pm2 startup
pm2 save
```

## 🤝 Contribuição

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 👨‍💻 Autor

**Felipe Voigt Postai (FLP)**
- Email: flpvoigt@gmail.com
- LinkedIn: [felipevoigt](https://linkedin.com/in/felipevoigt)
- GitHub: [flpvoigt](https://github.com/flpvoigt)

## 📞 Suporte

Para suporte, envie um email para flpvoigt@gmail.com ou abra uma issue no GitHub.

---

⭐ Se este projeto te ajudou, considere dar uma estrela!
