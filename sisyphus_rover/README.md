# Generating slides from markdown

```bash
pandoc -t html5 --template=../template-revealjs.html --standalone --section-divs \
    --variable theme="black" \
    --variable transition="linear" \
    --variable revealjs-url="../reveal.js" \
    slides.md -o slides.html

# View in browser
firefox slides.html
```
