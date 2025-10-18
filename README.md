# 🍋 App de Receita de Limonada com Jetpack Compose

Um aplicativo simples para Android, desenvolvido em Kotlin com Jetpack Compose, que demonstra como criar uma receita de limonada passo a passo. O projeto destaca o uso de componentes modernos da UI do Android e foca em como tornar elementos de texto clicáveis usando `Modifier.clickable`.

![Badge do Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![Badge do Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white)
![Badge do Jetpack Compose](https://img.shields.io/badge/Jetpack%20Compose-4285F4?style=for-the-badge&logo=jetpack-compose&logoColor=white)

## 🎯 Objetivo do Projeto

Este aplicativo foi criado como um exemplo didático para desenvolvedores que estão aprendendo Jetpack Compose. O principal destaque é a implementação de interatividade em um componente `Text`, uma tarefa comum no desenvolvimento de interfaces de usuário.

## ✨ Funcionalidades

* Interface de usuário simples e intuitiva construída 100% com Compose.
* Guia passo a passo para fazer limonada.
* Exemplo prático e isolado de como usar `Modifier.clickable` em um `Text`.

## 🛠️ Como Usar o Clique no Texto com Modifier

Em Jetpack Compose, a interatividade é adicionada aos componentes através de `Modifiers`. Para tornar um `Text` clicável, aplicamos o `Modifier.clickable`. Este modificador intercepta os eventos de toque e executa uma ação que definimos.

Veja o exemplo de código abaixo:

```kotlin
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.padding
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp

/**
 * Um Composable que exibe um texto que pode ser clicado.
 *
 * @param onTextoClicado A função lambda que será executada quando o texto for clicado.
 */
@Composable
fun TextoClicavelExemplo(onTextoClicado: () -> Unit) {
    Text(
        text = "Clique aqui para o próximo passo!",
        color = Color.Blue,
        fontWeight = FontWeight.Bold,
        fontSize = 18.sp,
        modifier = Modifier
            .padding(16.dp)
            .clickable {
                // Ação a ser executada quando o texto for clicado
                onTextoClicado()
            }
    )
}

@Preview(showBackground = true)
@Composable
fun PreviewTextoClicavel() {
    TextoClicavelExemplo(onTextoClicado = {
        // No aplicativo real, você poderia navegar para outra tela,
        // exibir uma mensagem, ou atualizar um estado.
        println("O texto foi clicado!")
    })
}
