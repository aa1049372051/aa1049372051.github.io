Title: How to use supabase in a Next.js project

URL Source: https://xiaole-9709.xlog.app/how-to-use-supabase-in-a-Next-js-project

Published Time: 2023-08-16T07:58:05.000Z

Markdown Content:
What is supabase[#](#what-is-supabase)
--------------------------------------

[supabase](https://supabase.com/) 是一个替代 Firebase 的开源 BaaS 项目。其提供了各种现代应用所需的稳定、强大、易于使用和可扩展的后端功能。Supabase 基于 PostgreSQL 数据库和 RESTful API 构建，并提供身份验证、实时数据推送、存储和其他一些常见的后端服务。

不需要买服务器，只需掌握简单的 SQL 语句和数据库知识就可以创建一个后端服务。当然它的功能是非常强大的，这篇文章只介绍如何在 Next.js 中使用。

Using supabase[#](#using-supabase)
----------------------------------

> Detailed reading of the official documentation is required for learning tasks.

According to the content in the section [Use Supabase with NextJS](https://supabase.com/docs/guides/getting-started/quickstarts/nextjs) of the official documentation, the usage steps are as follows:

Here I use supabase to store the number of views for a blog.

### Creating a project and setting up tables and data[#](#creating-a-project-and-setting-up-tables-and-data)

Create a project through [https://app.supabase.com/projects](https://app.supabase.com/projects)

![Image 1: new project](https://ipfs.crossbell.io/ipfs/QmUmBYCcG9MyMRe9JKNhH341qHKADe9TGxxUpYJ4Gi3enp?img-quality=75&img-format=auto&img-onerror=redirect&img-width=3840)

Create a table named "Views" in the SQL editor or the graphical interface of the Database.

![Image 2: database](https://ipfs.crossbell.io/ipfs/QmQcRBNBXXvh2UjQV27WBHkw66TnYpzkFr56UoA2knFwji?img-quality=75&img-format=auto&img-onerror=redirect&img-width=1920)

Here, create the "Views" table using the graphical interface by clicking "New table" in the top right corner of the Database.

![Image 3: create table](https://ipfs.crossbell.io/ipfs/QmWwCgpKdbpVBhjjGTa3LnkqQQKJKtrLfsX6bxsayc5VJN?img-quality=75&img-format=auto&img-onerror=redirect&img-width=3840)

The "slug" in the columns represents the title of the blog, and "count" represents the corresponding blog's view count.

### Creating a Next.js project[#](#creating-a-nextjs-project)

npx create-next-app@latest --typescript


![Image 4: image.png](https://ipfs.crossbell.io/ipfs/QmYcthrVDGC4h7YU3KQLkQPDHbmV6GqDFRM86mwwA1b5QH?img-quality=75&img-format=auto&img-onerror=redirect&img-width=3840)

### Installing supabase-js[#](#installing-supabase-js)

npm install @supabase/supabase-js


### Creating supabase[#](#creating-supabase)

Create a folder named "lib" in the root directory, and create a file named "supabase.ts" inside it.

import { createClient } from '@supabase/supabase-js';

const supabaseUrl = process.env.NEXT_PUBLIC_SUPABASE_URL as string;
const supabaseKey = process.env.NEXT_PUBLIC_SUPABASE_KEY as string;
export const supabase = createClient(supabaseUrl, supabaseKey);


The project\_url and supabase\_key can be found in the project's settings.

![Image 5: image.png](https://ipfs.crossbell.io/ipfs/QmatvJLNTMXy5pTwGWH8uYMSX5jsm9cZn3yZ5s5umyuv9u?img-quality=75&img-format=auto&img-onerror=redirect&img-width=3840)

It is not recommended to expose the key, so it can be stored in env.local.

> 💡 tips: In Next.js, when using env.local, you need to add the prefix NEXT\_PUBLIC, otherwise an error will occur.

### CRUD[#](#crud)

Detailed commands can be found in the [JavaScript](https://supabase.com/docs/reference/javascript/installing) documentation.

When opening a blog post page, you need to retrieve the view count of the current blog. You can use:

Create an index.ts file in the pages/api/views directory:

import { supabase } from '@/lib/supabase';
import type { NextApiRequest, NextApiResponse } from 'next';

export default async function handler(
req: NextApiRequest,
res: NextApiResponse
) {
try {
let { data } = await supabase.from('Views').select('*');
return res.status(200).json(data);
} catch (e: any) {
console.log(e);
return res.status(500).json({ message: e.message });
}
}


By writing SQL-like statements, you can retrieve all the data from the Views table.

You can also pass the slug as a parameter through a POST request to retrieve the corresponding data.

At the same time, when opening a blog post page, you also need to increment the view count of the current blog. You can use a POST request to pass the slug parameter:

fetch(`/api/views/${slug}`, {
method: 'POST'
});


Create a file named `[slug].ts` in the pages/api/views directory:

import { supabase } from '@/lib/supabase';
import type { NextApiRequest, NextApiResponse } from 'next';

export default async function handler(
req: NextApiRequest,
res: NextApiResponse
) {
try {
const slug = req.query?.slug as string;
if (!slug) {
return res.status(400).json({ message: 'Slug is required.' });
}

const { data } = await supabase
.from('Views')
.select('count')
.eq('slug', slug);

const views = !data?.length ? 0 : Number(data[0].count);

if (req.method === 'POST') {
if (views === 0) {
await supabase.from('Views').insert({ count: views + 1, slug: slug });

return res.status(200).json({
total: views + 1
});
} else {
await supabase
.from('views')
.update({ count: views + 1 })
.eq('slug', slug);
return res.status(200).json({
total: views + 1
});
}
}

if (req.method === 'GET') {
return res.status(200).json({ total: views });
}
} catch (e: any) {
console.log(e);
return res.status(500).json({ message: e.message });
}
}


Use insert for creating and update for updating. This way, the view count can be stored in supabase.

Other features[#](#other-features)
----------------------------------

Supabase also supports bucket storage. In my project, I store the og image in supabase.

![Image 6: image.png](https://ipfs.crossbell.io/ipfs/QmXn1M3nfPTAjJBwxbJ2jJjxbQTD1A5MPEoQndJVeyLgbU?img-quality=75&img-format=auto&img-onerror=redirect&img-width=640)

I will continue using supabase in the upcoming projects as a replacement for Firebase.