---
project: ant-design-charts
stars: 2001
description: A React Chart Library
url: https://github.com/ant-design/ant-design-charts
---

@ant-design/charts
==================

A React chart library, based on G2, G6, X6, L7.

Website • Quick Start • Examples • FAQ •

Case
----

### Statistical charts

✨ Features
----------

-   Easy to use
-   TypeScript
-   Pretty & Lightweight
-   Responsive
-   Storytelling

📦 Installation
---------------

$ npm install @ant-design/charts

🔨 Usage
--------

import React from 'react';
import { Line } from '@ant-design/charts';

const Page: React.FC \= () \=> {
  const data \= \[
    { year: '1991', value: 3 },
    { year: '1992', value: 4 },
    { year: '1993', value: 3.5 },
    { year: '1994', value: 5 },
    { year: '1995', value: 4.9 },
    { year: '1996', value: 6 },
    { year: '1997', value: 7 },
    { year: '1998', value: 9 },
    { year: '1999', value: 13 },
  \];

  const props \= {
    data,
    xField: 'year',
    yField: 'value',
  };

  return <Line {...props} />
};
export default Page;

Preview

Development
-----------

Clone locally:

$ git clone git@github.com:ant-design/ant-design-charts.git
$ cd ant-design-charts
$ pnpm install
$ pnpm build:lib & pnpm start

🤝 How to Contribute
--------------------

Your contributions are always welcome! Please Do have a look at the issues first.

📧 Contact us
-------------

DingTalk group number: `44788198` .

License
-------

MIT
