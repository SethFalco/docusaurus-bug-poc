# Bad Title for MDX Files

These work as expected, the output page has a title of `Privacy Policy | My Site`:

```mdx
# Privacy Policy

…

For any questions, please email [Seth Falco](mailto:seth@falco.fun).
```

```mdx
import PKG from '../../package.json';

# Privacy Policy

…

export function Author() {
  return (
    <a href={`mailto:${PKG.author.email}`} target="_blank" rel="noopener noreferrer">
      {PKG.author.name}
    </a>
  );
}

For any questions, please email <Author/>.
```

But this does not work as expected, the title is just `My Site`:

```mdx
import PKG from '../../package.json';

export function Author() {
  return (
    <a href={`mailto:${PKG.author.email}`} target="_blank" rel="noopener noreferrer">
      {PKG.author.name}
    </a>
  );
}

# Privacy Policy

…

For any questions, please email <Author/>.
```
