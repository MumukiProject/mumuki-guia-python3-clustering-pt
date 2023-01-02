Para responder à segunda afirmação, você pode achar útil usar a operação `describe` (se ainda não o fez).

🥱 E se você não quiser fazer o mesmo gráfico 4 vezes, você pode querer usar uma repetição, mas certificando-se de chamar `plt.show()` após cada gráfico para que eles não se sobreponham:

```python
for column in iris.columns:
 # ...seu gráfico aqui...
 plt.show()
```
