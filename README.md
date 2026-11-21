# xeixos-corp.github.io

The root site of the Xeixos-corp GitHub organisation, used for one thing:
Seixo's invite links.

- `.well-known/apple-app-site-association` tells iOS that links under `/c`
  open the Seixo app (and Seixo Dev) when it is installed. Apple requires this
  file at the root of a domain, which is why it cannot live in the
  `Seixo-Legal` repository.
- `c/index.html` is what an invite link shows when Seixo is not installed:
  how to install it, and a button that opens the invite once it is.
- `.nojekyll` makes GitHub Pages serve the `.well-known` folder, which Jekyll
  would otherwise skip.

The invite code is in the part of the link after `#`, which browsers never
send to a server, so GitHub never receives it. The page loads nothing from
anywhere else and sets no cookies.

How invites work: `supabase/migrations/0037_invites.sql` and
`app/src/transport/invites.ts` in <https://github.com/Xeixos-corp/seixo>.
