![logo](https://github.com/user-attachments/assets/ec1bed23-d8bb-4213-bfb8-c23f02ac3146)

# Game-Desert-Fox
Para conquistar sua vitória, colete todas as moedas de ouro que foram perdidas durante a fuga do imperador. Não deixe que os guardas te pegarem! Use as espadas!

Jogo desenvolvimento para a disciplina de Desenvolvimento de Jogos do curso de Sistemas de Informação da UEMG.
# Plataforma 2D - Jogo em Unity

## Sobre o Jogo

Este é um jogo de plataforma 2D desenvolvido na Unity utilizando C#. O objetivo é coletar todas as moedas presentes em cada fase, totalizando 20 moedas, derrotar inimigos (após coletar um item especial) e progredir entre fases, mantendo a quantidade de moedas coletadas. O jogo também possui um sistema de vidas e checkpoints.

#Existem 12 moedas na Fase 1 e 8 moedas na Fase 2. O player só avança para a próxima fase se coletar todas as moedas da fase atual. Após coletar todas as moedas da Fase 2 a mensagem de vitória é exibida depois volta para a tela de menu.

Não morra na Fase 2.
## Requisitos

- Unity (versão recomendada 2021 ou superior)
- C# para desenvolvimento de scripts

## Como Jogar

1. Controle o personagem pelo ambiente utilizando as teclas direcionais, direita e esquerda
2. Dê pulo simples, duplo e triplo com a tecla de espaço.
3. Colete moedas para acumular pontos.
4. Pegue o item especial (espada) para poder derrotar inimigos.
5. Evite cair em armadilhas ou tocar em inimigos sem o poder especial.
6. Avance para o próximo nível ao coletar todas as moedas necessárias da fase.

## Principais Mecânicas

- **Movimentação da Câmera**: Segue o jogador e ajusta limites.
- **Coleta de Moedas**: Contabiliza pontuação e desbloqueia novos níveis.
- **Sistema de Checkpoint**: Mantém moedas coletadas em fases avançadas.O contador é zerado, porém a pontuação acumulado continua.
- **Sistema de Vidas**: O jogador tem 3 vidas; ao perder todas, o jogo reinicia.
- **Inimigos**: Podem ser derrotados após coletar o item especial ou se o player pular na cabeça deles.
- **Morte do Jogador**: Reinicia a fase com as regras de moeda conforme a fase.
- **Música e Sons**: Controlados pelo `MusicController` e eventos do jogo.

## Estrutura do Código

```csharp
// Exemplo de estrutura de script GameController
public class GameController : MonoBehaviour
{
    public static GameController gc;
    public int moedas;
    public int vidas = 3;

    void Awake()
    {
        if (gc == null)
        {
            gc = this;
            DontDestroyOnLoad(gameObject);
        }
        else if (gc != this)
        {
            Destroy(gameObject);
        }
    }
}
```

- `GameController`: Controla a pontuação, vidas e transição de fases.
- `PlayerVida`: Gerencia a vida do jogador e reinicializa o jogo se necessário.
- `Inimigo`: Define o comportamento dos inimigos e verifica se podem ser derrotados.
- `ItemColetavel`: Permite que o jogador colete o item especial para derrotar inimigos.
- `NextLevel`: Gerencia a troca de fase e verifica condições para avançar.
- `Plataforma`: Controla plataformas móveis no jogo.
- `Destruidor`: Mata o jogador ao tocar em certas áreas.
- `Menu`: Gerencia a navegação entre cenas no jogo.
- `MusicController`: Mantém a música ativa entre as cenas.

## Como Executar

1. Abra o projeto na Unity.
2. Configure a cena inicial no **Build Settings**.
3. Clique em "Play" para testar o jogo.

## Melhorias Futuras

- Adicionar mais fases e desafios.
- Implementar um sistema de upgrades para o personagem.
- Criar uma tela de configurações para ajuste de áudio e controles.
- Melhorar a IA dos inimigos.

## Autor

Desenvolvido por Vitoria Arruda Andrade.

