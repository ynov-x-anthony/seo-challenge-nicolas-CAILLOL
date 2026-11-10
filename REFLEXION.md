# REFLEXION.md : à compléter

1. `robots.txt` empêche-t-il, à lui seul, le duplicate content entre
   `/produits?tri=prix` et `/produits?tri=prix-asc` ? Pourquoi ?

Non. `robots.txt` agit seulement sur l'exploration, pas sur la
      déduplication. Les deux URLs sont différentes et affichent le même
      contenu, et rien dans `robots.txt` ne dit à Google laquelle est la
      référence. Une page bloquée peut même rester indexée si un lien
      externe pointe vers elle.

2. Pourquoi la balise canonique est-elle l'outil adapté ici, plutôt que
   `robots.txt` ou une meta `noindex` ?

La canonique indique explicitement à Google la version de référence
      et regroupe les signaux SEO sur une seule URL. Avec `robots.txt`,
      Google ne pourrait pas lire la page ni sa canonique. Avec `noindex`,
      la variante serait retirée de l'index, mais sans transférer ses
      signaux vers l'autre URL.

3. Si demain `/admin` existe sur ce site et ne doit jamais être exploré par
   Google, quelle ligne ajoutes-tu dans `robots.txt` ?

`Disallow: /admin` sous `User-agent: *`.
  