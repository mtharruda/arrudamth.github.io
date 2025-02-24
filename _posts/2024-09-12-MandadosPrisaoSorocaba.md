---
layout: post
title: Mais de 40 pessoas são procuradas pela Justiça há pelos menos dez anos na região de Sorocaba, indicam dados do CNJ
lead: Python, Selenium, Flourish 
---
*Reportagem publicada no **g1**, em dezembro de 2024.* 
<br>
Automatização via Python, utilizando o Selenium, de buscas no sistema do Conselho Nacional de Justiça por nome. Para análise, biblioteca Pandas, e gráficos produzidos no Flourish.
<br>


<   

    for index, row in mandados_sorocaba.iterrows():
    
    processo = row['Número']
        
    #Primeiro, vamos passar nosso número de processo
    driver.find_element(By.XPATH, "/html/body/app-root/div/div/div[2]/div/app-pesquisa-peca/div[1]/p-fieldset/fieldset/div/div/form/div[14]/span/p-inputmask/input").send_keys(f'{processo}')
    
    driver.implicitly_wait(5)
    
    #Então, vamos clicar em PESQUISAR
    driver.find_element(By. XPATH, '/html/body/app-root/div/div/div[2]/div/app-pesquisa-peca/div[1]/p-fieldset/fieldset/div/div/form/div[18]/button[2]/span[1]').click()
   
    #driver.implicitly_wait(5)
    
    time.sleep(5)

    #E, depois, abrir o link do processo
    driver.find_element(By. XPATH, '/html/body/app-root/div/div/div[2]/div/app-pesquisa-peca/div[1]/p-datatable/div/div[1]/table/tbody/tr/td[1]/span[2]/span').click()
    
    driver.implicitly_wait(5)
    
    time.sleep(5)

    nome = driver.find_element(By.XPATH, '/html/body/app-root/div/div/div[2]/div/app-resumo-peca/div/p-panel/div/div[2]/div[1]/div[4]/table/tbody/tr/td').text
    crime = driver.find_element(By.XPATH, '/html/body/app-root/div/div/div[2]/div/app-resumo-peca/div/p-panel/div/div[2]/div[1]/p-datatable/div/div[1]/table/tbody/tr/td/span').text
    
    #pena = driver.find_element(By.XPATH, '/html/body/app-root/div/div/div[2]/div/app-resumo-peca/div/p-panel/div/div[2]/div[1]/p[19]/span').text

    print(nome, crime)

    dados.append({
    "Nome": nome,
    "Crime(s)": crime,
    })
    
    time.sleep(5)
    
    driver.find_element(By.XPATH, '/html/body/app-root/div/div/div[2]/div/app-resumo-peca/div/p-panel/div/div[2]/div[2]/p-footer/div/button[3]').click()
   
    time.sleep(5)> 

[Código](https://github.com/mtharruda/bnmp-scraper) disponibilizado após publicação. 
[Leia aqui.](https://g1.globo.com/sp/sorocaba-jundiai/noticia/2024/12/09/mais-de-40-pessoas-sao-procuradas-pela-justica-ha-pelos-menos-dez-anos-na-regiao-de-sorocaba-indicam-dados-do-cnj.ghtml)

[^fn-sample]: Handy! Now click the return link to go back.
