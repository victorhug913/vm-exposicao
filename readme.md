Pneumonia associada à ventilação mecânica - Análise de fatores de risco
================

Obs: Como, por padrão, são registradas as infecções hospitalares no
banco de dados, os pacientes que não tenham registros de PAV foram
considerados negativos para tal evolução.

Quanto à ordem das colunas, testei outras bibliotecas para calcular o
odds e aparentemnete o problema está na biblioteca mesmo, ela considera
as colunas em ordem inversa.

# Estatística descritiva

    ## 1) Não PAV     2) PAV 
    ##       1897         30

# Análise quanto ao sexo

    ## $data
    ##            i
    ## d           1) Não PAV 2) PAV Total
    ##   Feminino         804     10   814
    ##   Masculino       1093     20  1113
    ##   Total           1897     30  1927
    ## 
    ## $measure
    ##            odds ratio with 95% C.I.
    ## d           estimate     lower    upper
    ##   Feminino   1.00000        NA       NA
    ##   Masculino  1.47118 0.6849096 3.160083
    ## 
    ## $p.value
    ##            two-sided
    ## d           midp.exact fisher.exact chi.square
    ##   Feminino          NA           NA         NA
    ##   Masculino  0.3279673    0.3566009  0.3194344
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# Análise quanto ao tempo de VM

Observação: Revisei os dias de VM e realmente não tem dados missing
aqui, todos os pacientes com VM positivo, tem valores em dias de VM,
apesar de alguns extremamente baixos (do tipo 0,01) e dois pacientes com
valor igual a 0. Creio que o software do hospital calcule esse tempo
automaticamente a partir do momento de entrada e de saída do paciente e
por isso aconteceu isso. Não pode ser considerado 2 dias de VM aqui,
porque nenhuma pneumonia é considerada Pneumonia associada à ventilação
mecânica se o paciente tiver menos de 2 dias de VM, portanto a
incidência nesse grupo é igual a 0 e o ODDS dá infinito com ele travado.

    ## Warning in chisq.test(xx, correct = correction): Chi-squared approximation may
    ## be incorrect

    ## Warning in chisq.test(xx, correct = correction): Chi-squared approximation may
    ## be incorrect

    ## Warning in chisq.test(xx, correct = correction): Chi-squared approximation may
    ## be incorrect

    ## $data
    ##                     i
    ## d                    1) Não PAV 2) PAV Total
    ##   1) Até 5 dias            1526      1  1527
    ##   2) 5 a 10 dias            171      5   176
    ##   3) 10 a 14 dias            64      6    70
    ##   4) 14 dias ou mais        136     18   154
    ##   Total                    1897     30  1927
    ## 
    ## $measure
    ##                     odds ratio with 95% C.I.
    ## d                     estimate     lower     upper
    ##   1) Até 5 dias        1.00000        NA        NA
    ##   2) 5 a 10 dias      44.61988  5.182754  384.1459
    ##   3) 10 a 14 dias    143.06250 16.971896 1205.9277
    ##   4) 14 dias ou mais 201.97059 26.757808 1524.4940
    ## 
    ## $p.value
    ##                     two-sided
    ## d                      midp.exact fisher.exact   chi.square
    ##   1) Até 5 dias                NA           NA           NA
    ##   2) 5 a 10 dias     6.267905e-05 6.155131e-05 3.997184e-09
    ##   3) 10 a 14 dias    3.905522e-08 3.882415e-08 6.018187e-26
    ##   4) 14 dias ou mais 0.000000e+00 1.411684e-18 1.158299e-38
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# Idosos e não idosos.

Considera-se idosos pessoas com 60 anos ou mais.

    ## $data
    ##               i
    ## d              1) Não PAV 2) PAV Total
    ##   1) Não Idoso        640      7   647
    ##   2) Idoso           1257     23  1280
    ##   Total              1897     30  1927
    ## 
    ## $measure
    ##               odds ratio with 95% C.I.
    ## d              estimate     lower    upper
    ##   1) Não Idoso 1.000000        NA       NA
    ##   2) Idoso     1.672917 0.7140395 3.919464
    ## 
    ## $p.value
    ##               two-sided
    ## d              midp.exact fisher.exact chi.square
    ##   1) Não Idoso         NA           NA         NA
    ##   2) Idoso      0.2360434     0.329463  0.2312095
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# Internação por Covid-19

As UTIs 3 e 4 foram abertas e receberam exclusivamente pacientes de
Covid-19, portanto, considerou-se tais pacientes como internados por
Covid-19. Nenhuma outra UTI recebeu pacientes que fossem sabidamente
diagnosticados para a doença.

    ## Warning in chisq.test(xx, correct = correction): Chi-squared approximation may
    ## be incorrect

    ## $data
    ##                  i
    ## d                 1) Não PAV 2) PAV Total
    ##   1) Não Covid-19       1795     21  1816
    ##   2) Covid-19            102      9   111
    ##   Total                 1897     30  1927
    ## 
    ## $measure
    ##                  odds ratio with 95% C.I.
    ## d                 estimate   lower    upper
    ##   1) Não Covid-19 1.000000      NA       NA
    ##   2) Covid-19     7.542017 3.36874 16.88525
    ## 
    ## $p.value
    ##                  two-sided
    ## d                   midp.exact fisher.exact   chi.square
    ##   1) Não Covid-19           NA           NA           NA
    ##   2) Covid-19     2.911713e-05 2.606525e-05 9.287243e-09
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# Diabetes mellitus insulino dependente

    ## Warning in chisq.test(xx, correct = correction): Chi-squared approximation may
    ## be incorrect

    ## $data
    ##        i
    ## d       1) Não PAV 2) PAV Total
    ##   Não         1810     28  1838
    ##   Sim           87      2    89
    ##   Total       1897     30  1927
    ## 
    ## $measure
    ##      odds ratio with 95% C.I.
    ## d     estimate     lower    upper
    ##   Não 1.000000        NA       NA
    ##   Sim 1.486043 0.3483771 6.338887
    ## 
    ## $p.value
    ##      two-sided
    ## d     midp.exact fisher.exact chi.square
    ##   Não         NA           NA         NA
    ##   Sim  0.5654419     0.646663   0.590108
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# Diabetes mellitus não insulino dependente

    ## Warning in chisq.test(xx, correct = correction): Chi-squared approximation may
    ## be incorrect

    ## $data
    ##        i
    ## d       1) Não PAV 2) PAV Total
    ##   Não         1621     18  1639
    ##   Sim          276     12   288
    ##   Total       1897     30  1927
    ## 
    ## $measure
    ##      odds ratio with 95% C.I.
    ## d     estimate    lower    upper
    ##   Não 1.000000       NA       NA
    ##   Sim 3.915459 1.865318 8.218879
    ## 
    ## $p.value
    ##      two-sided
    ## d       midp.exact fisher.exact   chi.square
    ##   Não           NA           NA           NA
    ##   Sim 0.0008388914  0.000683449 0.0001047729
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# Doença Pulmonar Obstrutiva Crônica

    ## Warning in chisq.test(xx, correct = correction): Chi-squared approximation may
    ## be incorrect

    ## $data
    ##        i
    ## d       1) Não PAV 2) PAV Total
    ##   Não         1864     27  1891
    ##   Sim           33      3    36
    ##   Total       1897     30  1927
    ## 
    ## $measure
    ##      odds ratio with 95% C.I.
    ## d     estimate    lower    upper
    ##   Não 1.000000       NA       NA
    ##   Sim 6.276094 1.813547 21.71952
    ## 
    ## $p.value
    ##      two-sided
    ## d     midp.exact fisher.exact   chi.square
    ##   Não         NA           NA           NA
    ##   Sim  0.0191917   0.01720114 0.0009150241
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# Etilismo

    ## Warning in chisq.test(xx, correct = correction): Chi-squared approximation may
    ## be incorrect

    ## $data
    ##        i
    ## d       1) Não PAV 2) PAV Total
    ##   Não         1756     28  1784
    ##   Sim          141      2   143
    ##   Total       1897     30  1927
    ## 
    ## $measure
    ##      odds ratio with 95% C.I.
    ## d      estimate     lower    upper
    ##   Não 1.0000000        NA       NA
    ##   Sim 0.8895643 0.2097598 3.772527
    ## 
    ## $p.value
    ##      two-sided
    ## d     midp.exact fisher.exact chi.square
    ##   Não         NA           NA         NA
    ##   Sim  0.9477289            1  0.8737927
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# Fibrilação atrial crônica

``` {r
atrial, echo=FALSE}
QuiQuadradoCompleto(df$PAV,df$
                      .Atrial.Crônica);
```

# Hipertensao Arterial Sistêmica

    ## $data
    ##        i
    ## d       1) Não PAV 2) PAV Total
    ##   Não          924      7   931
    ##   Sim          973     23   996
    ##   Total       1897     30  1927
    ## 
    ## $measure
    ##      odds ratio with 95% C.I.
    ## d     estimate    lower    upper
    ##   Não 1.000000       NA       NA
    ##   Sim 3.120247 1.332539 7.306309
    ## 
    ## $p.value
    ##      two-sided
    ## d      midp.exact fisher.exact  chi.square
    ##   Não          NA           NA          NA
    ##   Sim 0.005481145  0.005616884 0.005787984
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# Insuficiência cardíaca congestiva

    ## Warning in chisq.test(xx, correct = correction): Chi-squared approximation may
    ## be incorrect

    ## $data
    ##        i
    ## d       1) Não PAV 2) PAV Total
    ##   Não         1838     27  1865
    ##   Sim           59      3    62
    ##   Total       1897     30  1927
    ## 
    ## $measure
    ##      odds ratio with 95% C.I.
    ## d     estimate    lower   upper
    ##   Não 1.000000       NA      NA
    ##   Sim 3.461394 1.021254 11.7319
    ## 
    ## $p.value
    ##      two-sided
    ## d     midp.exact fisher.exact chi.square
    ##   Não         NA           NA         NA
    ##   Sim 0.08373493   0.06951534 0.03385302
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# IRC Não dialítica

    ## Warning in chisq.test(xx, correct = correction): Chi-squared approximation may
    ## be incorrect

    ## $data
    ##        i
    ## d       1) Não PAV 2) PAV Total
    ##   Não         1820     27  1847
    ##   Sim           77      3    80
    ##   Total       1897     30  1927
    ## 
    ## $measure
    ##      odds ratio with 95% C.I.
    ## d     estimate     lower   upper
    ##   Não 1.000000        NA      NA
    ##   Sim 2.626263 0.7797077 8.84595
    ## 
    ## $p.value
    ##      two-sided
    ## d     midp.exact fisher.exact chi.square
    ##   Não         NA           NA         NA
    ##   Sim  0.1586474    0.1254633  0.1055544
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# Obesidade

    ## Warning in chisq.test(xx, correct = correction): Chi-squared approximation may
    ## be incorrect

    ## $data
    ##        i
    ## d       1) Não PAV 2) PAV Total
    ##   Não         1794     26  1820
    ##   Sim          103      4   107
    ##   Total       1897     30  1927
    ## 
    ## $measure
    ##      odds ratio with 95% C.I.
    ## d     estimate     lower   upper
    ##   Não 1.000000        NA      NA
    ##   Sim 2.679612 0.9179928 7.82176
    ## 
    ## $p.value
    ##      two-sided
    ## d     midp.exact fisher.exact chi.square
    ##   Não         NA           NA         NA
    ##   Sim  0.1034655   0.08095686 0.06071129
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# Tabagismo

    ## $data
    ##        i
    ## d       1) Não PAV 2) PAV Total
    ##   Não         1567     22  1589
    ##   Sim          330      8   338
    ##   Total       1897     30  1927
    ## 
    ## $measure
    ##      odds ratio with 95% C.I.
    ## d     estimate     lower   upper
    ##   Não 1.000000        NA      NA
    ##   Sim 1.726722 0.7621362 3.91212
    ## 
    ## $p.value
    ##      two-sided
    ## d     midp.exact fisher.exact chi.square
    ##   Não         NA           NA         NA
    ##   Sim  0.2052956    0.2216788   0.185257
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# Paciente com Câncer

    ## Warning in chisq.test(xx, correct = correction): Chi-squared approximation may
    ## be incorrect

    ## $data
    ##        i
    ## d       1) Não PAV 2) PAV Total
    ##   Não         1606     28  1634
    ##   Sim          291      2   293
    ##   Total       1897     30  1927
    ## 
    ## $measure
    ##      odds ratio with 95% C.I.
    ## d      estimate      lower    upper
    ##   Não 1.0000000         NA       NA
    ##   Sim 0.3942072 0.09340131 1.663781
    ## 
    ## $p.value
    ##      two-sided
    ## d     midp.exact fisher.exact chi.square
    ##   Não         NA           NA         NA
    ##   Sim   0.186617    0.3014433  0.1892877
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# Paciente Crônico

    ## Warning in chisq.test(xx, correct = correction): Chi-squared approximation may
    ## be incorrect

    ## $data
    ##        i
    ## d       1) Não PAV 2) PAV Total
    ##   Não         1682     25  1707
    ##   Sim          215      5   220
    ##   Total       1897     30  1927
    ## 
    ## $measure
    ##      odds ratio with 95% C.I.
    ## d     estimate     lower    upper
    ##   Não 1.000000        NA       NA
    ##   Sim 1.564651 0.5927657 4.130019
    ## 
    ## $p.value
    ##      two-sided
    ## d     midp.exact fisher.exact chi.square
    ##   Não         NA           NA         NA
    ##   Sim  0.3708395    0.3786082  0.3621199
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# Reinternação

    ## Warning in chisq.test(xx, correct = correction): Chi-squared approximation may
    ## be incorrect

    ## $data
    ##        i
    ## d       1) Não PAV 2) PAV Total
    ##   Não         1726     29  1755
    ##   Sim          171      1   172
    ##   Total       1897     30  1927
    ## 
    ## $measure
    ##      odds ratio with 95% C.I.
    ## d     estimate      lower    upper
    ##   Não 1.000000         NA       NA
    ##   Sim 0.348054 0.04712033 2.570899
    ## 
    ## $p.value
    ##      two-sided
    ## d     midp.exact fisher.exact chi.square
    ##   Não         NA           NA         NA
    ##   Sim  0.2952657    0.5127783  0.2788958
    ## 
    ## $correction
    ## [1] FALSE
    ## 
    ## attr(,"method")
    ## [1] "Unconditional MLE & normal approximation (Wald) CI"

# ODDs Ratio Ajustado

    ## Carregando pacotes exigidos: mfx

    ## Carregando pacotes exigidos: sandwich

    ## Carregando pacotes exigidos: lmtest

    ## Carregando pacotes exigidos: zoo

    ## 
    ## Attaching package: 'zoo'

    ## The following objects are masked from 'package:base':
    ## 
    ##     as.Date, as.Date.numeric

    ## Carregando pacotes exigidos: MASS

    ## Carregando pacotes exigidos: betareg

    ## Carregando pacotes exigidos: readr

    ## Waiting for profiling to be done...

    ##                                OR       2.5 %      97.5 %
    ## (Intercept)           0.007007206 0.002860759  0.01440797
    ## Idoso22) Idoso        1.286114516 0.561029536  3.31715231
    ## Covid1922) Covid-19   5.220717239 2.029127889 12.28339326
    ## DMNID2Sim             3.417776980 1.548715969  7.29156936
    ## DPOC.Não.Terminal2Sim 2.712074623 0.558436535  9.80298301
    ## IRC.Não.Dialítica2Sim 1.542623841 0.347842945  4.77183612
