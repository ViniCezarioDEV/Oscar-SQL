# Oscar-SQL

### Quantos Oscars Natalie Portman ganhou?
`SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_do_indicado LIKE '%portman%' AND vencedor = 'true';`<br>
3 oscars

### Amy Adams já ganhou algum Oscar?
`SELECT COUNT(*) FROM indicados_ao_oscar WHERE nome_do_indicado LIKE '%amy adams%' AND vencedor = 'true';`<br>
não, mas já concorreu a 6

### A série de filmes Toy Story ganhou um Oscar em quais anos?
`SELECT * FROM indicados_ao_oscar WHERE nome_do_filme LIKE '%toy story%' AND vencedor = 1;`<br>
sim, 2 em 2011, e 1 em 2020

### A partir de que ano que a categoria "Actress" deixa de existir?
`SELECT categoria , ano_cerimonia FROM indicados_ao_oscar WHERE categoria LIKE '%actress%';`<br>
depois de 1976

### Quem ganhou o primeiro Oscar para Melhor Atriz? Em que ano?
`SELECT nome_do_indicado, categoria, ano_cerimonia, vencedor FROM indicados_ao_oscar WHERE categoria LIKE '%actress%' AND vencedor = 'true' ORDER BY ano_cerimonia;`<br>
Janet Gaynor, no ano de 1928

### Na campo "Vencedor", altere todos os valores com "true" para 1 e todos os valores "false" para 0.
`UPDATE indicados_ao_oscar SET vencedor = 1 WHERE vencedor = 'true';`<br>
`UPDATE indicados_ao_oscar SET vencedor = 0 WHERE vencedor = 'false';`<br>

### Em qual edição do Oscar "Crash" concorreu ao Oscar?
`SELECT * FROM indicados_ao_oscar WHERE nome_do_filme = 'Crash';`<br>
no ano de 2006

### O filme Central do Brasil aparece no Oscar?
`SELECT * FROM indicados_ao_oscar WHERE nome_do_filme LIKE '%Central do Brasil%';`<br>
não, ele não aparece

### Inclua no banco 3 filmes que nunca foram nem nomeados ao Oscar, mas que merecem ser.
`INSERT INTO indicados_ao_oscar(ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, nome_do_filme, vencedor)VALUES (1982, 2024, 97, 'ACTOR', 'Kurt Russell', 'The Thing', 0);`<br>
`INSERT INTO indicados_ao_oscar(ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, nome_do_filme, vencedor)VALUES (1998, 2024, 97, 'ACTOR', 'Jeff Bridges','The Big Lebowski', 0);`<br>
`INSERT INTO indicados_ao_oscar(ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, nome_do_filme, vencedor)VALUES (2001, 2024, 97, 'ACTOR', 'Jake Gyllenhaal', 'Donnie Darko', 0);`<br>

### Denzel Washington já ganhou algum Oscar?
`SELECT nome_do_indicado, vencedor FROM indicados_ao_oscar WHERE nome_do_indicado LIKE '%Denzel Washington%' AND vencedor = 1;`<br>
sim, 2 oscar

### Quais os filmes que ganharam o Oscar de Melhor Filme?
`SELECT nome_do_filme FROM indicados_ao_oscar WHERE categoria LIKE '%BEST PICTURE%' AND vencedor = 1;`<br>
Lawrence of Arabia<br>
Tom Jones<br>
My Fair Lady<br>
The Sound of Music<br>
A Man for All Seasons<br>
In the Heat of the Night<br>
Oliver!<br>
Midnight Cowboy<br>
Patton<br>
The French Connection<br>
The Godfather<br>
The Sting<br>
The Godfather Part II<br>
One Flew over the Cuckoo's Nest<br>
Rocky<br>
Annie Hall<br>
The Deer Hunter<br>
Kramer vs. Kramer<br>
Ordinary People<br>
Chariots of Fire<br>
Gandhi<br>
Terms of Endearment<br>
Amadeus<br>
Out of Africa<br>
Platoon<br>
The Last Emperor<br>
Rain Man<br>
Driving Miss Daisy<br>
Dances With Wolves<br>
The Silence of the Lambs<br>
Unforgiven<br>
Schindler's List<br>
Forrest Gump<br>
Braveheart<br>
The English Patient<br>
Titanic<br>
Shakespeare in Love<br>
American Beauty<br>
Gladiator<br>
A Beautiful Mind<br>
Chicago<br>
The Lord of the Rings: The Return of the King<br>
Million Dollar Baby<br>
Crash<br>
The Departed<br>
No Country for Old Men<br>
Slumdog Millionaire<br>
The Hurt Locker<br>
The King's Speech<br>
The Artist<br>
Argo<br>
12 Years a Slave<br>
Birdman or (The Unexpected Virtue of Ignorance)<br>
Spotlight<br>
Moonlight<br>
The Shape of Water<br>
Green Book<br>
Parasite<br>
Nomadland<br>
CODA<br>
Everything Everywhere All at Once<br>
Oppenheimer

### Bonus: Quais os filmes que ganharam o Oscar de Melhor Filme e Melhor Diretor na mesma cerimonia?
`SELECT categoria, nome_do_filme, ano_cerimonia, vencedor FROM indicados_ao_oscar WHERE categoria LIKE '%DIRECTING%' AND categoria LIKE '%BEST PICTURE%';`<br>
nenhum

### Bonus: Denzel Washington e Jamie Foxx já concorreram ao Oscar no mesmo ano?
`SELECT ano_cerimonia, nome_do_indicado FROM indicados_ao_oscar WHERE nome_do_indicado LIKE '%Denzel Washington%' AND nome_do_indicado LIKE '%Jamie Foxx%';`<br>
não
