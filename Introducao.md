## 1.2 Por que Python para análise de dados?

### Python como aglutinador
- Python é uma linguagem capaz de integrar, conectar e coordenar facilmente outras linguagens ou sistemas
- Isso é especialmente útil para software legados, geralmente escritos em C, C++ ou FORTRAN (eficientes, mas difíceis de manter e modificar)
- Python possui muitas bibliotecas que fazem ponte com C, C++ e FORTRAN, ou seja, pode ser usado como **interface** para controlar o que está sendo feito com código rápido escrito em outra linguagem

### Resolvendo o problema de duas linguagens
- Em muitas empresas, é comum pesquisar e prototipar novas ideias usando linguagens de programação mais especializadas como o R e, posteriormente, portar essas ideias para que façam parte de um sistema de produção maior escrito em Java, C#, C++...
- Python, no entanto, consegue ser adequado não apenas para pesquisa e prototipagem, mas também para criação de sistemas de produção
- Existem benefícios organizacionais significativos quando tanto os pesquisadores quanto os engenheiros de software usam o mesmo conjunto de ferramentas de programação
- Em muitos casos, aproveitar ao máximo o Python demandará programação em uma linguagem de baixo nível, como C ou C++, e a criação de vinculações (bindings) Python para esse código
- Outra alternativa é usar a tecnologia de compilador "just-in-time" (JIT) oferecida por bibliotecas, como o Numba, que traduzem o código Python para código de máquina otimizado

### Por que não Python?
- Há casos em o uso de Python não é o mais adequado, mesmo com o *tempo do programador* sendo frequentemente mais caro do que o *tempo da CPU*
- Em aplicações com latências muito baixas ou exigentes quanto aos requisitos de utilização dos recursos, o maior tempo gasto na programação com uma linguagem de nível mais baixo pode ser justificado
- Python pode ser desafiador para criação de aplicações **multithread altamente concorrentes**, principalmente com muitas threads limitadas por CPU (CPU-bound — o gargalo está no processamento, não na espera por recursos externos)
- Isso ocorre por causa do GIL (Global Interpreter Locker), um mecanismo que impede que o interpretador execute mais de uma instrução Python de cada vez
- Não há paralelismo (e sim concorrência) para código Python puro, apenas para operações I/O e bibliotecas como NumPy (o GIL é liberado)
- Em multiprocessamento, há paralelismo (processos separados = GILs separados)
- Uma solução é utilizar extensões C do Python, que executam código em paralelo sem ser afetadas pelo GIL, contanto que não precisem interagir regularmente com objetos Python