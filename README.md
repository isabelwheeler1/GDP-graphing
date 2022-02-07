# GDP-graphing
Graphing LifExp vs. gdpPercap for US, Canada and Australia


```{r}
life5060 <- read.csv("https://raw.githubusercontent.com/ds202-at-isu/materials/master/01_collaborative-environment/data/gapminder-5060.csv")
head(life5060)
```

```{r}
canada <- life5060 %>% filter(country == "Canada")
head(canada)
```

```{r}
canada %>% 
  ggplot(aes(x = year, y = lifeExp)) +
  geom_line()
```

```{r}
canada %>% filter(year == 1957)
canada_fixed <- canada %>% mutate(
  lifeExp = replace(lifeExp, year==1957, 69.96)  
)

canada_fixed
```

```{r}
canada_fixed %>% ggplot(aes(x = year, y = lifeExp)) +
  geom_line()
```
