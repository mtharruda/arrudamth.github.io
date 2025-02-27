---
layout: post
title: Desaparecido político mais jovem do país e estudante torturado até a morte
lead: Python, Google Gemini, Flourish 
---
Com base no Relatório Final da Comissão da Verdade, automatizei via `Google Gemini`, a extração do local de nascimento e local de morte para a produção do mapa. A visualização, por sua vez, foi finalizada no `Flourish`. [Leia aqui.](https://g1.globo.com/sp/sorocaba-jundiai/noticia/2025/01/27/desaparecido-politico-mais-jovem-do-pais-e-estudante-torturado-ate-a-morte-mapa-conta-historia-de-sorocabanos-vitimas-da-ditadura.ghtml) 
<br> 

{% highlight js linenos %}
def selecionar_informacao(texto, prompt):
  model = genai.GenerativeModel("gemini-1.5-flash")
  response = model.generate_content(prompt)
  print(response.text) #model = GenerateText()
  return response>
  
resultados = []
for i, row in bd.iterrows():
  texto = row['Biografia']
  prompt = f"Extraia o local de nascimento e morte do {texto}. E retorne desta forma: Nascimento: Cidade (UF), Morte: Cidade (UF). Caso não esteja especificado, resuma"
  response = selecionar_informacao(texto, prompt)
  resultado = response.text
  resultados.append(resultado)
  print("-----")
  time.sleep(15)
bd['LocalMorte'] = resultados>
{% endhighlight %}

<div class="flourish-embed flourish-map" data-src="visualisation/21773785"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/21773785/thumbnail" width="100%" alt="map visualization" /></noscript></div>

[^fn-sample]: Handy! Now click the return link to go back.
