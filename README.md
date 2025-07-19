# heroku-buildpack-xlsx2csv-fix

What is Xlsx2csv?

[Xlsx2csv](http://github.com/dilshod/xlsx2csv) converts XLSX files to CSV format. It handles large XLSX files. Fast and easy to use.

You can initially install the Xlsx2csv package into your application by using heroku-buildpack-apt:
- [heroku/heroku-buildpack-apt](https://github.com/heroku/heroku-buildpack-apt) or
- [velizarn/heroku-buildpack-apt](https://github.com/velizarn/heroku-buildpack-apt)

This buildpack applies a fix to shebang line in xlsx2csv.py file.

Currently this fix is only applicable to Heroku-24 stack.<br />
To ommit this limitation, please use 
https://github.com/velizarn/heroku-buildpack-xlsx2csv-fix#allstacks branch instead.

## Example

If xlsx2csv.py file starts with this line:

```
#!/usr/bin/python3
```

this buildpack will change it based on actual python location e.g.:

```
/app/.heroku/python/bin/python
```

Python versions / Heroku stacks

<table>
  <tr>
    <th>Python version</th>
    <th>Heroku-22 *</th>
    <th>Heroku-24 **</th>
  </tr>
  <tr>
    <td>3.12.x</td>
    <td>fix to be applied</td>
    <td>fix to be applied</td>
  </tr>
  <tr>
    <td>3.11.x</td>
    <td>fix to be applied</td>
    <td>fix to be applied</td>
  </tr>
  <tr>
    <td>3.10.x</td>
    <td><i>fix not needed</i></td>
    <td>fix to be applied</td>
  </tr>
  <tr>
    <td>3.9.x</td>
    <td>?</td>
    <td>?</td>
  </tr>
</table>
<sub>* Fix not needed if built-in Python installation is used<br />
** The system Python installation in the base image is now only available at build time, and not also at app run time, you must add the Python buildpack to your app</sub>

## License

MIT

## Resources

- https://pypi.org/project/xlsx2csv/
- https://devcenter.heroku.com/articles/getting-started-with-python
- https://devcenter.heroku.com/categories/python-support
- https://devcenter.heroku.com/articles/stack
- https://devcenter.heroku.com/articles/heroku-24-stack
- https://en.wikipedia.org/wiki/Shebang_(Unix)
