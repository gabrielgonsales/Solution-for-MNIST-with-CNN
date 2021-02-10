MNIST – VISÃO COMPUTACIONAL E CÂMERA - DRIVELESS

Cada item a seguir é enumerado conforme a sequência do código no arquivo ipynb.

1) Importação da biblioteca do TensorFlow e verificada sua versão. 
2) Importação do Data Set com todos os dígitos e sua descompactação.
3) Antes de realizar a normalização dos dados no passo 4, eu achei interessantes visualizar os dados do tensor e da imagem de um elemento do banco de dados para verificar se o código estava funcionando. Para a plotagem do tensor foi utilizado o comando print. Para a visualização da imagem foi utilizado o comando plt.show da biblioteca do matplotlib.
4) Normalização dos dados. A normalização acontece para facilitar, simplificar e otimizar o processamento da rede neural.
5) Plotagem dos dados já citados no item 3 após a normalização.
6) Desenvolvimento do modelo
a) Inicialização da rede neural utilizando o Keras. Aqui foi criado o objeto model da classe Sequential.
b) Criação da primeira camada, ou Input Layer. Aqui foi aplicado o comando Flatten para converter as matrizes multidimensionais em colunas singulares que ,posteriormente, são então alimentados à rede neural para processamento.
c) Criação das Hidden Layers. Aqui foi utilizado a função de ativação ReLu, ou Rectified Linear Unit, a fim de dar um tratamento não-linear para o problema. Foi utilizado devido à sua simplicidade se comparado a outros métodos de ativação. Ademais, eu utilizei 3 Hidden Layers com 256 neurons, porque o problema do MNIST não é tão complexo. Uma coisa que achei curioso foi que, eu testei antes com 2 Hidden Layers e 128 neurons e me ocorreu que a precisão foi menor e a perda foi maior no caso com 2 Hidden Layers. Ademais, eu utilizei um Epoch de 10, não sei se é demais, imagino que sim, pois as perdas se mantiveram constantes após alguns testes no sétimo Epoch.
d) Criação da Output Layer. Assim como as Hidden Layers, esta também é uma camada Densa, na qual foi utilizada a função de ativação SoftMax, a qual faz o uso da distribuição de probabilidade para a conexão total.
e) Compilação do modelo. Para fazer a compilação eu tive que pesquisar mais algumas coisas, do ponto de vista global eu percebi que para o optimizer, o argumento Adam é bom devido à sua fácil implementação e eficiência computacional. Eu pesquisei outros, como Stochastic Gradient Descent, que não deixa de ser uma vertente mais ampla do Adam. Este foi o link que eu pesquisei o adam : 
https://machinelearningmastery.com/adam-optimization-algorithm-for-deep-learning/#:~:text=Adam%20is%20a%20replacement%20optimization,sparse%20gradients%20on%20noisy%20problems. 
Ademais, para o argumento loss, a utilização do sparse_categorical_crossentropy, é vantajosa pois ela mantém os objetos como inteiros. Já para o argumento metrics, a utilização do accuracy serve para computar a frequência com que o valor real é igual ao valor esperado. 
7) Treinamento do modelo utilizando o banco de dados de treinamento.
8) Cálculo da validation loss e da validation accuracy do banco de dados de teste para o modelo. Aqui foi obtida uma precisão(accuracy) e uma perda(loss) próximos. Entretanto, a precisão(accuracy) obtida foi um pouco menor e a perda(loss) um pouco maior, o que é de se esperar.
9) Salvando o modelo 
10) Realização da prediction. O novo modelo de previsão retorna one-hot arrays, que são distribuições de densidade de probabilidade. Assim, faz-se necessário o uso da biblioteca NumPy para visualizar os dados da prediction.
11) Utilização da biblioteca NumPy.
12) Vizualização da prediction.
