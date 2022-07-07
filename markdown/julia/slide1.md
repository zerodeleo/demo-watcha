### HOOKS UNDER THE HOODS

###### CODESNIPPET:
```javascript
import { useState } from 'react';
console.log(useState);
```

###### CONSOLE:
```javascript
f useState(initialState) {
      const dispatcher = resolveDispatcher();
      return dispatcher.useState(initialState);
    }
```

https://github.com/zerodeleo/hooks-under-the-hoods