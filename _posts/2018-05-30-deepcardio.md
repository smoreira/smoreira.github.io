---
layout: tutorial
comments: true
title: Deep Cardio 
subtitle: "Análise de sons de batimentos cardíacos para identificação de problemas cardiovasculares"
date: 2018-05-30
true-dt: 2018-05-30
tags: [Post]
author: "Sandro Moreira"
header-img: "img/deepcardio.jpg"
modal-id: 7
thumbnail: /img/tumbDeepCardio.jpg
description: Projeto que utiliza Deep Learning para encontrar anormalidades nos batimentos cardíacos.

---

## Descrição

Segundo a Organização Mundial de Saúde (OMS), as doenças cardiovasculares são a principal causa de morte no mundo, no Brasil, 300 mil pessoas sofrem infartos todos os anos; em 30% dos casos o ataque cardíaco é fatal. (BRASIL, 2017).
A classificação e análise do som do coração (Fonocardiograma ou PCG - Phonocardiogram) desempenha um papel importante no diagnóstico precoce e prevenção de doenças cardiovasculares, mais especificamente as valvares. Quando uma das válvulas cardíacas se torna defeituosa pode resultar em estenose (estreitamento) ou regurgitação (vazamento). 
Por se tratar de doenças assintomáticas, os pacientes normalmente levam anos até obterem o diagnóstico definitivo e iniciarem tratamentos adequados. 
O diagnóstico tardio, quando o paciente passa por episódios de dores no peito (angina), cansaço, indica que o mesmo já está em condições críticas e, em sua maioria com idade avançada, o que diminui as chances de reabilitação após intervenção cirúrgica necessária em casos críticos para troca das válvulas cardíacas. 
De acordo com Leatham (1975), as primeiras classificações automatizadas utilizando PCG foram realizados há mais de 50 anos, e ao longo dos últimos anos, vários estudos foram realizados utilizando técnicas de análise de sinais, aprendizado de máquina como modelos ocultos de Markov, SVM (Support Vector Machine), etc. no entanto ainda é um desafio a classificação de áudios com ruídos externos, baixa qualidade e gravações em ambiente não clínicos.  


## Metodologia

A ideia embrionária dessa proposta de estudo surgiu durante as discussões de projetos finais da disciplina de Redes Neurais Profundas do programa de pós graduação em Ciência da Computação da Universidade Federal de Goiás. 
A prova de conceito obtida com o modelo proposto obteve uma avaliação da taxa de acurácia de 86.00% (oitenta e seis por centro) e foi apresentada na Mostra de Inteligência Artificial realizada no Instituto de Informática (INF) em agosto de 2017 e reapresentada na exposição realizada no Hotel Castro’s em Goiânia-GO.  
A arquitetura inicialmente proposta é baseada em redes neurais convolucionais (CNN - Convolutional Neural Network) desenvolvida utilizando a biblioteca de código livre Google TensorFlow.
Para os testes iniciais, como na prova de conceito, serão utilizados os dados publicados por Physionet (2016), que contém 4.340 gravações obtidas de 1.072 indivíduos, totalizando 233.512 sons cardíacos coletados de indivíduos saudáveis e pacientes com várias condições, como doença valvar cardíaca e doença arterial coronariana, em ambientes clínicos e não clínicos.
 Os arquivos de áudio para treinamento da inteligência artificial serão convertidos para espectrograma, que é uma representação gráfica do som através da Transformada de Fourier, de acordo com Figueiredo (1977), obtendo-se assim arquivos de imagens conforme ilustrado na figura abaixo.

<img src="/img/spectro.png" alt="spectro" class="img-responsive thumbnail pull-right" style="margin-left:5%; width: 90%;">

 Segundo SZEGEDY (2016), as redes convolucionais estão no centro da maioria das soluções de visão computacional para uma ampla variedade de tarefas. Desde 2014, as redes convolucionais muito profundas começaram a se tornar convencionais, produzindo ganhos substanciais em vários pontos de referência. A figura 2 apresenta um esquema de como é proposta a análise do espectrograma do áudio pela rede convolucional.

<img src="/img/convolution_cardio.png" alt="convolucional" class="img-responsive thumbnail pull-right" style="margin-left:0%; width: 90%;">


Os padrões contidos no áudio de um batimento cardíaco podem indicar a patologia presente nas válvulas cardíacas conforme afirma Guyton e Hall (2011)  e é apresentado na figura abaixo.

<img src="/img/phonocardio.png" alt="phonocardio" class="img-responsive thumbnail pull-right" style="margin-left:5; width: 25%;">

Uma interface de usuário será desenvolvida para realizar a captura de áudio através de microfone acoplado a um estetoscópio e submissão à classificação pelo sistema inteligente. O estetoscópio deverá ser posicionado em um dos focos de auscultação cardíaca para realização da gravação.  De acordo com Guyton e Hall (2011) existem quatro pontos focais: aórtico, pulmonar, tricúspide e mitral.

## Imprensa

Matéria Portal G1 (https://g1.globo.com/go/goias/noticia/apos-a-morte-do-pai-professor-de-goias-cria-aplicativo-para-apontar-doencas-cardiacas-de-forma-simples-e-rapida.ghtml)

Matéria no Jornal O Popular (https://www.opopular.com.br/editorias/cidades/drama-familiar-inspira-inven%C3%A7%C3%A3o-1.1453740)

Revista UFG (https://issuu.com/ufgascom/docs/jornal_ufg_92_para_impress__o)

Notícias UFG (https://www.ufg.br/n/104438-aplicativo-desenvolvido-na-ufg-encontra-anomalias-cardiacas)

Matéria Jornal Serra Dourada (https://www.youtube.com/watch?v=Q4lBR5zC1Lg&t=55s)


## Referências

BRASIL; Governo do Brasil; Doenças cardiovasculares são principal causa de morte no mundo. Disponível em: 
(http://www.brasil.gov.br/saude/2017/09/doencas-cardiovasculares-sao-principal-causa-de-morte-no-mundo) Acesso em 06/11/2017

SCHEFFER, M. et al, Demografia Médica no Brasil 2015. Departamento de Medicina Preventiva, Faculdade de Medicina da USP. Conselho Regional de Medicina do Estado de São Paulo. Conselho Federal de Medicina. São Paulo: 2015, 284 páginas. ISBN: 978-85-89656-22-1

LEATHAM, A. Auscultation of the heart and phonocardiography. Churchill Livingstone: 1975

GUYTON, A.C, HALL, J. E.; Textbook of Medical Physiology 12th Ed. – Saunders Elsevier, Philadelphia-PA,  2011. ISBN: 978-1-4160-4574-8

PHYSIONET; An open access database for the evaluation of heart sound algorithms. Physiological Measurement 2016

FIGUEREDO, D.G; Análise de Fourier e Equações Diferenciais Parciais. Rio de Janeiro: IMPA-CNPq, 1977. 274 p.

SZEGEDY, C, ET AL; Rethinking the Inception Architecture for Computer Vision, 2016, disponível em: (https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Szegedy_Rethinking_the_Inception_CVPR_2016_paper.pdf) acesso em 06/11/2017
