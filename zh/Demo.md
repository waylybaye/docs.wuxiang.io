# Demo

## Discuz! (chiphell)

```json
{
name: 'Discuz!',
initial_url: 'https://www.chiphell.com/forum.php',
user_agent: 'desktop',

pages: [{
  match: '/**/*forum.php',

  components: [
    {
      type: 'list',
      settings: {
        media_size: '20x19',
        style: 'simple',
      },
      selectors: {
        sections: {
          __selector__: '*div.bmw',
          text: 'h2',

          items: {
            __selector__: '*td.fl_g',
            media: '.fl_icn_g img@src',
            title: 'dt > a',
            summary: 'dd',
            url: 'dt > a @href',
            comments: 'em.xw0',
            date: 'dd a',
          }
        }
      },
    }
  ]
}, {
  match: '/**/*forum-*.html',
  components: [
    {
      type: 'list',
      settings: {
        media_size: '18x18',
        header: '置顶主题',
        style: 'simple',
      },

      selectors: {
        items: {
          __selector__: '#threadlisttableid > tbody[id^=stick]',
          label: 'th.new em',
          media: '.icn img',
          title: 'th a.xst',
          url: 'th a.xst @href',
          author: 'tr td:last-child cite',
          date: 'tr td:last-child em',
          comments: 'td.num a',
        },
        next_page_url: 'a.nxt @href',
      }
    },
    {
      type: 'list',
      settings: {
        media_size: '18x18',
        style: 'simple',
        header: '版块主题',
      },

      selectors: {
        items: {
          __selector__: '#threadlisttableid > tbody[id^=normal]',
          label: 'th.new em',
          media: '.icn img',
          // title: 'th.new a.xst',
          title: 'th a.xst',
          // url: 'th.new a.xst @src',
          url: 'th a.xst @href',
          author: 'tr td:last-child cite',
          date: 'tr td:last-child em',
          comments: 'td.num a',
        },
        next_page_url: 'a.nxt @href',
      }
    }
  ]
}, {
  match: '/**/*thread-*.html',
  components: [
    {
      type: 'gallery',
      selectors: {
        __selector__: 'img.zoom',
        url: '@zoomfile',
      }
    },
    {
      type: 'article',
      selectors: {
        ___selector__: '#postlist > div[id]',
        title: 'h1 span',
        author: 'a.xs1',
        content: 'td.t_f',
        date: 'td.plc em',
      }
    },
    {
      type: 'list',
      settings: {
        media_size: '120x120px',
        style: 'comments',
        header: '主题回复',
      },
      selectors: {
        __selector__: '#postlist > div:nth-of-type(n+1)',
        content: '.t_fsz',
        author: 'a.xw1',
        media: '.avatar img',
        date: '.authi em'
      }
    }
  ]
}]
}
```
