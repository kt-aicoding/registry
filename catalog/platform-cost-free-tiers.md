# Platform Cost And Free-Tier Reference

Last verified: 2026-06-28.

This is a public, sanitized operating reference for AI coding infrastructure cost checks. It records current read-only CLI evidence, official pricing/free-tier sources, and follow-up actions. It must not include raw account IDs, emails, tokens, cookies, project refs, environment IDs, invoices, or private dashboard data.

## Current Resource Snapshot

| Platform | Read-only status | Current evidence | Cost-risk note |
| --- | --- | --- | --- |
| Vercel | verified | 4 projects visible from CLI | Hobby can still incur usage/add-on risk through metered resources; verify Usage and Invoices in dashboard. |
| Supabase | verified | 1 active project visible; demo work consolidated into `kevinten10` | Project count risk is controlled; confirm organization plan and overage in Supabase Billing. |
| Cloudflare | verified with recheck note | `cli-tools/docs/local-cli-system.md` records Pages=1, KV=2, D1=1, R2=1, Queues=1 from 2026-06-28 read-only checks | Cloudflare is an infra cost surface to monitor. Use dashboard or supported CLI output before making deletion, budget, or plan decisions. |
| Netlify | verified with recheck note | `cli-tools/docs/local-cli-system.md` records site list count 0; registry spot-check also confirmed auth/current-directory state | Confirm team plan and monthly credits in the Netlify dashboard before relying on cost conclusions. |
| Fly.io | verified | apps list count is 0 | No apps found by CLI; confirm organization billing only if historical invoices exist. |
| Railway | externally blocked | CLI reports unauthorized | Run `railway login` before resource or cost checks. |
| CloudBase | verified | 1 normal personal environment visible | Confirm package renewal and pay-as-you-go usage in Tencent Cloud console. |
| GitHub | verified | keyring auth works; `kt-aicoding` repos enumerated | Actions is free for public repos and quota-limited for private repos; confirm billing dashboard for private Actions/Packages use. |

## Official Free-Tier And Pricing Notes

| Platform | Official source | Practical boundary |
| --- | --- | --- |
| Vercel | [Vercel pricing docs](https://vercel.com/docs/pricing), [Vercel pricing page](https://vercel.com/pricing) | Hobby includes free usage for many resources, but Vercel bills metered infrastructure and DX resources when included amounts or add-ons apply. Watch Functions, Image Optimization, Blob, Observability, Builds, and Pro add-ons. |
| Supabase | [Supabase billing docs](https://supabase.com/docs/guides/platform/billing-on-supabase), [Supabase pricing](https://supabase.com/pricing) | Free plan grants two free projects across organizations where the user is Owner/Admin. Paid plans include fixed subscription plus variable usage; compute is per project, and launching more projects can increase monthly compute costs. |
| Cloudflare Workers | [Workers pricing](https://developers.cloudflare.com/workers/platform/pricing/), [Workers & Pages plans](https://www.cloudflare.com/plans/developer-platform/) | Workers Free includes daily request/CPU limits; Workers Paid starts at the platform's paid tier. Queue consumers and Workers execution can add cost on paid plans. |
| Cloudflare R2 | [R2 pricing](https://developers.cloudflare.com/r2/pricing/) | Standard storage free tier includes 10 GB-month/month, 1M Class A ops/month, 10M Class B ops/month, and free Internet egress. Beyond that, storage and operations are billed. |
| Cloudflare D1 | [D1 pricing](https://developers.cloudflare.com/d1/platform/pricing/) | Workers Free includes daily D1 read/write limits and 5 GB total storage. Paid plan includes monthly read/write/storage allowance, then overage. Wrangler/dashboard queries count as usage. |
| Cloudflare KV | [Workers KV pricing](https://developers.cloudflare.com/kv/platform/pricing/) | Workers Free includes limited daily reads/writes/deletes/list requests and 1 GB stored data. Dashboard and Wrangler operations count as usage. |
| Cloudflare Queues | [Queues pricing](https://developers.cloudflare.com/queues/platform/pricing/) | Workers Free includes 10,000 operations/day; Workers Paid includes monthly operations then overage. A typical delivered message costs write + read + delete operations. |
| Netlify | [Netlify pricing](https://www.netlify.com/pricing/), [Netlify Free plan announcement](https://www.netlify.com/blog/introducing-netlify-free-plan/), [credit-based pricing changelog](https://www.netlify.com/changelog/netlify-pricing-update-introducing-credit-based-plans/) | Free plan is $0 and now uses monthly credits; older free-plan docs list bandwidth/build/function allowances. Use the dashboard's account usage/credits view as source of truth. |
| Railway | [Railway pricing docs](https://docs.railway.com/pricing), [Railway plans docs](https://docs.railway.com/pricing/plans), [Railway free trial](https://docs.railway.com/pricing/free-trial), [Railway cost control](https://docs.railway.com/pricing/cost-control) | Free trial starts with a one-time credit and later limited free credit; Hobby is a paid minimum usage plan. Configure usage limits in dashboard before deploying persistent services. |
| Fly.io | [Fly pricing](https://fly.io/pricing/), [Fly resource pricing docs](https://fly.io/docs/about/pricing/) | CLI shows no apps. Fly is usage-priced; dashboard/invoices are authoritative for any historical or organization-level charges. |
| CloudBase | [Tencent CloudBase product pricing](https://intl.cloud.tencent.com/document/product/1266/70296), [CloudBase product page](https://www.tencentcloud.com/products/tcb) | CloudBase uses package + pay-as-you-go style billing. The local CLI shows a normal personal environment; dashboard is required to confirm renewal, package, and overage. |
| GitHub Actions | [GitHub Actions billing docs](https://docs.github.com/en/billing/concepts/product-billing/github-actions) | Standard GitHub-hosted runners are free for public repositories. Private repos use plan quotas for minutes/storage/cache; overages require billing settings and are charged to the repository owner. |

## Operating Guidance

- Use provider CLIs for read-only resource discovery, then provider dashboards for actual invoices and usage dollars.
- Do not delete resources, change plans, set budgets, or enable hard limits without explicit user approval.
- Keep Supabase demo development in the single `kevinten10` project unless the user explicitly approves a separate project.
- Treat Cloudflare as a current infra cost surface because Pages, KV, D1, R2, and Queues resources are recorded in the CLI system snapshot; dashboard usage is still authoritative for cost.
- Treat Railway as unknown until login is refreshed.
- For dashboard-only billing pages, record only plan/usage conclusions and source names, not account identifiers, invoice details, or payment information.

## Follow-Up Checklist

- [ ] Vercel dashboard: confirm Usage and Invoices for the current billing period.
- [ ] Supabase dashboard: confirm organization plan, invoices, and usage overage.
- [ ] Cloudflare dashboard: confirm Workers plan, R2 storage/ops, D1 row reads/writes/storage, KV ops/storage, Queues ops.
- [ ] CloudBase console: confirm package renewal, auto-renewal, and pay-as-you-go usage.
- [ ] Railway CLI/dashboard: re-authenticate and confirm whether any projects/services exist.
- [ ] GitHub billing: check private Actions/Packages usage if private repos or paid runners are active.
