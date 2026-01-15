# ☕ Coffee Shop - Android App

Uma aplicação Android moderna de loja de café desenvolvida com **Jetpack Compose** e **Material Design 3**.

[![Kotlin](https://img.shields.io/badge/Kotlin-1.9.0-purple.svg)](https://kotlinlang.org)
[![Jetpack Compose](https://img.shields.io/badge/Jetpack%20Compose-1.5.4-brightgreen.svg)](https://developer.android.com/jetpack/compose)
[![Material Design 3](https://img.shields.io/badge/Material%20Design-3-blue.svg)](https://m3.material.io/)
[![Min SDK](https://img.shields.io/badge/Min%20SDK-24-orange.svg)](https://developer.android.com/studio/releases/platforms)
[![Target SDK](https://img.shields.io/badge/Target%20SDK-34-orange.svg)](https://developer.android.com/studio/releases/platforms)

---

## 📱 Screenshots

<table>
  <tr>
    <td><img src="screenshots/home.png" width="200"/></td>
    <td><img src="screenshots/explore.png" width="200"/></td>
    <td><img src="screenshots/profile.png" width="200"/></td>
  </tr>
  <tr>
    <td align="center"><b>Home Screen</b></td>
    <td align="center"><b>Explore Screen</b></td>
    <td align="center"><b>Profile Screen</b></td>
  </tr>
  <tr>
    <td><img src="screenshots/detail.png" width="200"/></td>
    <td><img src="screenshots/cart.png" width="200"/></td>
    <td><img src="screenshots/navigation.png" width="200"/></td>
  </tr>
  <tr>
    <td align="center"><b>Detail Screen</b></td>
    <td align="center"><b>Cart Screen</b></td>
    <td align="center"><b>Bottom Navigation</b></td>
  </tr>
</table>

---

## ✨ Funcionalidades

### 🏠 Home Screen
- ✅ Banner promocional destacado
- ✅ Barra de pesquisa funcional
- ✅ Filtro por categoria (Espresso, Cappuccino, Latte, Tea, Beverages)
- ✅ Grid de cafés com imagens e ratings
- ✅ Badge no carrinho mostrando quantidade de items
- ✅ Estados de loading

### 🔍 Explore Screen
- ✅ Banner de ofertas especiais ("New Year Special")
- ✅ Seção de ofertas com descontos (Buy 2 Get 1, Weekend Special, Happy Hour)
- ✅ Coffee Stories (Origin Stories, Brewing Guide, Barista Tips)
- ✅ Cafés recomendados baseados em preferências
- ✅ Guia de métodos de preparação

### 👤 Profile Screen
- ✅ Avatar personalizado com iniciais
- ✅ Estatísticas do usuário (47 pedidos, 12 favoritos, 850 pontos)
- ✅ Informações de contacto (email, telefone)
- ✅ Menu de configurações (Notificações, Morada, Pagamento, Privacidade)
- ✅ Histórico de 5 pedidos com status
- ✅ Botão de logout estilizado

### 📋 Detail Screen
- ✅ Imagem em destaque do café
- ✅ Rating e descrição detalhada
- ✅ Seleção de tamanho (Small, Medium, Large)
- ✅ Controle de quantidade (+/-)
- ✅ Botão "Add to Cart" com feedback visual
- ✅ Ingredientes e informações extras

### 🛒 Cart Screen
- ✅ Lista de items no carrinho
- ✅ Controle individual de quantidade por item
- ✅ Remover items do carrinho
- ✅ Cálculo automático de subtotal, delivery e tax
- ✅ Total em destaque
- ✅ Dialog de confirmação antes do checkout
- ✅ Tela vazia estilizada com botão "Start Shopping"

### 🧭 Bottom Navigation
- ✅ 3 telas principais (Home, Explore, Profile)
- ✅ Ícones com indicador visual de seleção
- ✅ Esconde automaticamente em telas secundárias
- ✅ State preservation durante navegação

---

## 🏗️ Arquitetura

O projeto segue o padrão **MVVM (Model-View-ViewModel)** com **Jetpack Compose**.

```
app/src/main/java/com/example/lojacafe/
│
├── data/                          # Modelos de dados
│   ├── Coffee.kt                  # Modelo principal de café
│   ├── Category.kt                # Categorias de café
│   ├── Banner.kt                  # Banners promocionais
│   └── CartItem.kt                # Items do carrinho
│
├── viewmodel/                     # Lógica de negócio
│   └── CoffeeViewModel.kt         # ViewModel central (StateFlow)
│
├── ui/                            # Interface do usuário
│   ├── screens/                   # Telas da aplicação
│   │   ├── HomeScreen.kt          # Tela inicial
│   │   ├── ExploreScreen.kt       # Exploração e ofertas
│   │   ├── ProfileScreen.kt       # Perfil do usuário
│   │   ├── DetailScreen.kt        # Detalhes do café
│   │   └── CartScreen.kt          # Carrinho de compras
│   │
│   └── theme/                     # Tema da aplicação
│       ├── Color.kt               # Paleta de cores
│       ├── Theme.kt               # Configuração do tema
│       └── Type.kt                # Typography
│
├── navigation/                    # Sistema de navegação
│   └── Screen.kt                  # Definição de rotas
│
└── MainActivity.kt                # Activity principal + Bottom Navigation
```

### 📊 Fluxo de Dados

```
View (Composable)
    ↓
    ← observa StateFlow
    ↓
ViewModel
    ↓
    ← gerencia Estado
    ↓
Model (Data Classes)
```

---

## 🛠️ Tecnologias Utilizadas

### Core
- **Kotlin** - Linguagem de programação moderna
- **Jetpack Compose** - UI declarativa e moderna
- **Material Design 3** - Sistema de design Google
- **MVVM** - Arquitetura recomendada Android

### Jetpack Libraries
- **Navigation Compose** - Navegação type-safe
- **ViewModel** - Gestão de estado e ciclo de vida
- **StateFlow** - Reactive state management
- **Lifecycle** - Componentes lifecycle-aware

### Networking & Images
- **Coil** - Image loading com cache automático

### UI Components
- **LazyColumn/LazyRow** - Listas otimizadas
- **LazyVerticalGrid** - Grid responsivo
- **AlertDialog** - Diálogos Material 3
- **Bottom Navigation** - Navegação principal

---

## 📦 Dependências

```kotlin
dependencies {
    // Jetpack Compose
    implementation("androidx.compose.ui:ui:1.5.4")
    implementation("androidx.compose.material3:material3:1.1.2")
    implementation("androidx.compose.ui:ui-tooling-preview:1.5.4")
    implementation("androidx.activity:activity-compose:1.8.1")
    
    // Navigation
    implementation("androidx.navigation:navigation-compose:2.7.5")
    
    // ViewModel
    implementation("androidx.lifecycle:lifecycle-viewmodel-compose:2.6.2")
    implementation("androidx.lifecycle:lifecycle-runtime-ktx:2.6.2")
    
    // Coil para carregamento de imagens
    implementation("io.coil-kt:coil-compose:2.5.0")
    
    // Core
    implementation("androidx.core:core-ktx:1.12.0")
}
```

---

## 🚀 Como Executar

### Pré-requisitos
- Android Studio Hedgehog | 2023.1.1 ou superior
- JDK 11 ou superior
- Android SDK (Min SDK 24, Target SDK 34)
- Emulador Android ou dispositivo físico

### Passo a Passo

1. **Clone o repositório**
```bash
git clone https://github.com/seu-usuario/coffee-shop-app.git
cd coffee-shop-app
```

2. **Abra no Android Studio**
- File → Open
- Selecione a pasta do projeto
- Aguarde o Gradle sync

3. **Configure o emulador**
- Tools → Device Manager
- Crie um dispositivo virtual (recomendado: Pixel 5, API 34)

4. **Execute o projeto**
- Clique no botão Run ▶️
- Selecione o dispositivo/emulador
- Aguarde a instalação e abertura do app

---

## 📊 Dados Mockados

Atualmente a aplicação utiliza dados mockados para demonstração:

- **18+ cafés** em 5 categorias
- **4 cafés populares** em destaque
- **3 ofertas especiais** na tela Explore
- **4 coffee stories** educacionais
- **5 pedidos** no histórico do usuário

### 🔮 Integração Futura (Firebase)

A estrutura está preparada para integração com Firebase:
- Firebase Authentication (login/registro)
- Firestore Database (catálogo e pedidos)
- Firebase Storage (upload de imagens)
- Cloud Messaging (notificações push)

---

## 🎨 Design System

### Paleta de Cores

```kotlin
// Backgrounds
BackgroundDark = #1C1C1E    // Fundo principal
BackgroundCard = #2C2C2E    // Cards e elementos elevados

// Acentos
AccentOrange = #FF6F00      // Cor principal da marca
OrangeBrown = #D84315       // Gradientes
TextOrange = #FF8C42        // Texto em laranja

// Texto
TextWhite = #FFFFFF         // Texto principal
TextGray = #AAAAAA          // Texto secundário

// Estados
AccentGreen = #4CAF50       // Sucesso
ErrorRed = #E53935          // Erro/Cancelamento
```

### Typography
- **Headlines:** Roboto Bold (24sp - 32sp)
- **Body:** Roboto Regular (14sp - 16sp)
- **Captions:** Roboto Regular (12sp)

---

## 📈 Estatísticas do Projeto

- **Telas:** 5 completas
- **Produtos:** 18+ cafés
- **Categorias:** 6 (incluindo "All")
- **Funcionalidades:** 15+
- **Linhas de código:** ~2000+
- **Tempo de desenvolvimento:** 4-5 horas
- **Erros de compilação:** 0 ✅

---

## 🧪 Testes Realizados

### Testes Manuais
- ✅ Navegação entre todas as telas
- ✅ Adicionar items ao carrinho
- ✅ Remover items do carrinho
- ✅ Atualizar quantidades
- ✅ Filtros por categoria
- ✅ Busca de cafés
- ✅ Checkout completo
- ✅ Bottom navigation
- ✅ Rotação de tela
- ✅ Estados vazios

### Dispositivos Testados
- ✅ Pixel 5 (Emulador) - API 34
- ✅ Samsung Galaxy S21 - API 33
- ✅ Diferentes tamanhos de tela

---

## 🔄 Roadmap Futuro

### v1.1 (Próxima versão)
- [ ] Sistema de favoritos
- [ ] Animações de transição
- [ ] Modo claro/escuro
- [ ] Mais categorias de café

### v2.0 (Médio prazo)
- [ ] Firebase Authentication
- [ ] Firebase Realtime Database
- [ ] Notificações push
- [ ] Histórico real de pedidos
- [ ] Sistema de reviews e ratings

### v3.0 (Longo prazo)
- [ ] Integração com pagamento (Stripe)
- [ ] Rastreamento de pedidos em tempo real
- [ ] Mapa de lojas físicas
- [ ] Programa de fidelidade
- [ ] Multi-idioma (PT, EN, ES)

---

## 🤝 Contribuindo

Contribuições são bem-vindas! Siga estes passos:

1. Fork o projeto
2. Crie sua feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

### Diretrizes
- Siga o estilo de código Kotlin
- Adicione comentários em código complexo
- Teste suas alterações
- Atualize a documentação se necessário

---

## 📝 Licença

Este projeto é licenciado sob a MIT License - veja o arquivo [LICENSE](LICENSE) para detalhes.

---

## 👨‍💻 Autor

**Seu Nome**
- GitHub: [@Henrique_k18](https://github.com/seu-usuario)
- LinkedIn: 
- Email: 

---

## 🙏 Agradecimentos

- [Jetpack Compose](https://developer.android.com/jetpack/compose) pela incrível framework de UI
- [Material Design 3](https://m3.material.io/) pelo sistema de design
- [Coil](https://coil-kt.github.io/coil/) pelo excelente image loading
- [Cloudinary](https://cloudinary.com/) pelo hosting das imagens
- Comunidade Android dev pelo suporte e inspiração

---

## 📞 Suporte

Se encontrar algum problema ou tiver sugestões:
- 🐛 [Abra uma issue](https://github.com/seu-usuario/coffee-shop-app/issues)
- 💬 [Discussões](https://github.com/seu-usuario/coffee-shop-app/discussions)
- 📧 Email: seu.email@example.com

---

<div align="center">

### ⭐ Se gostou do projeto, deixe uma estrela! ⭐

**Desenvolvido com ☕ e ❤️**

</div>

---

## 📚 Recursos Adicionais

### Documentação Útil
- [Jetpack Compose Documentation](https://developer.android.com/jetpack/compose/documentation)
- [Material Design 3 Guidelines](https://m3.material.io/)
- [Kotlin Coding Conventions](https://kotlinlang.org/docs/coding-conventions.html)
- [MVVM Architecture Guide](https://developer.android.com/topic/architecture)

### Tutoriais Relacionados
- [Compose Navigation](https://developer.android.com/jetpack/compose/navigation)
- [State Management in Compose](https://developer.android.com/jetpack/compose/state)
- [ViewModel and LiveData](https://developer.android.com/topic/libraries/architecture/viewmodel)

---

**Última atualização:** Janeiro 2026
