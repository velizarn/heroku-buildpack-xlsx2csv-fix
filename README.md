# heroku-buildpack-xlsx2csv-fix

What is Xlsx2csv?

[Xlsx2csv](http://github.com/dilshod/xlsx2csv) converts XLSX files to CSV format. It handles large XLSX files. Fast and easy to use.

You can initially install the Xlsx2csv package into your application by using heroku-buildpack-apt:
- [heroku/heroku-buildpack-apt](https://github.com/heroku/heroku-buildpack-apt) or
- [velizarn/heroku-buildpack-apt](https://github.com/velizarn/heroku-buildpack-apt)

This buildpack applies a fix to shebang line in xlsx2csv.py file.

Currently this fix is only applicable to Heroku-24 stack.

## Example

If xlsx2csv.py file starts with this line:

```
#!/usr/bin/python3
```

this buildpack will change it based on actual python location e.g.:

```
/app/.heroku/python/bin/python
```

## License

MIT

## Resources

- https://pypi.org/project/xlsx2csv/
- https://devcenter.heroku.com/articles/getting-started-with-python
- https://devcenter.heroku.com/categories/python-support
- https://devcenter.heroku.com/articles/stack
- https://devcenter.heroku.com/articles/heroku-24-stack
- https://en.wikipedia.org/wiki/Shebang_(Unix)
