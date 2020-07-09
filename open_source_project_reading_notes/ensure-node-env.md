## Project Info

Git: https://github.com/Skyscanner/ensure-node-env

About: A script that helps ensure you have the correct node & npm versions installed in your environment.

## Note

- obtain local/global node module version string.
- use system specific EOL to create neat console logs.
- execute command line within js file synchronously.
- valiate a version string is within given range through semver.satifies function.

### getVersion

local bin folder path string

```
const localBinFolder = execSync('npm bin')
      .toString()
      .trim();
```

determine global/local env path

```
if (global) {
    env.PATH = env.PATH.replace(`${localBinFolder}${path.delimiter}`, '');
  } else {
    env.PATH = `${localBinFolder}${path.delimiter}${env.PATH}`;
  }
```

global version

```getVersion({ 'node --version', localBinFolder })```

local version

```getVersion({ 'node --version', localBinFolder, global: false })```


source code
```
const getVersion = ({ command, localBinFolder, global = true }) => {
  const env = { ...process.env };

  if (global) {
    env.PATH = env.PATH.replace(`${localBinFolder}${path.delimiter}`, '');
  } else {
    env.PATH = `${localBinFolder}${path.delimiter}${env.PATH}`;
  }

  return execSync(command, { env })
    .toString()
    .replace('v', '')
    .trim();
};
```

### Obtain node command line arguments

[process.argv](https://nodejs.org/api/process.html#process_process_argv)

```
const { argv } = process;
const verbose = argv.indexOf('-v') !== -1 || argv.indexOf('--verbose') !== -1;
const ignoreLocalBin =
argv.indexOf('-i') !== -1 || argv.indexOf('--ignore-local-bin') !== -1;
```

### Execute command line within node project

[execSync](https://nodejs.org/api/child_process.html#child_process_child_process_execsync_command_options) : a synchronous version of child_process.exec() that will block the Node.js event loop.

### Obtain system EOL

```import { EOL } from 'os';```

### Obtain system path delimiter

```${path.delimiter}```

### Validate semver

[semver.satisfies](https://github.com/npm/node-semver/blob/f56505b1c08856a7e6139f6ee5d4580f5f2feed8/functions/satisfies.js) : If you want to know if a version satisfies or does not satisfy a range, use the satisfies(version, range) function.
