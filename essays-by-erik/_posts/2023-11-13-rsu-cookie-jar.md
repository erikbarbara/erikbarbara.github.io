---
layout: post
title: The RSU Cookie Jar
---
> Who stole the cookie from the cookie jar?
> 
> — [Sesame Street](https://www.youtube.com/watch?v=_2qofl5LGg8){:target="_blank"}

If a company's valuation increases and its growth prospects taper enough, they'll switch from granting employees [Incentive Stock Options (ISOs)](/essays/2023/10/25/of-isos-and-edge-cases.html) to Restricted Stock Units (RSUs).

With RSUs, the company essentially _gives_ the employee company stock over a period of time.

## Double-Trigger RSUs

There are different _triggers_ on the RSUs that must be satisfied before the employee receives units of company stock. A time-based trigger is nearly always present on the RSUs. This is the same as ISO vesting where an employee must achieve tenure at a company. RSU grants typically have a one year cliff when an employee first joins the company; subsequent grants then vest quarterly.

Sometimes there's a second trigger on private company stock where not only must the employee be at the company a period of time before they receive the stock but the company must also experience a liquidity event like a public offering or an acquisition.

Until both triggers are met, employees aren't taxed by the government on their vested RSUs. In exchange, the IRS [requires](https://www.irs.gov/businesses/corporations/equity-stock-based-compensation-audit-techniques-guide){:target="_blank"} that there be a **substantial risk of forfeiture**. Often this risk comes in the form of expiration.

## Susan's RSUs

Let's go back to Susan. Widgets.io no longer grants stock options and instead has switched to RSUs. This happens when the future expected growth of a stock is much lower. If the value of a share is $1,000, it's far less likely to 100x again. So companies switch to RSU grants to incentivize employees joining.

When Susan joined Widgets.io 6 years ago, Susan received a grant for 1,000 double-trigger RSUs vesting over 4 years. 7 years later that initial grant is fully vested and the company shares are worth $2,000 each. But the bad news is that Widget.io is not planning on going public or being acquired anytime soon. And the worse news is that the RSU plan is written such that grants will expire after 8 years. So on paper Susan theoretically has $2M of stock that may just vanish in a year if the second trigger isn't met.

The company wants to retain Susan. If they start letting RSUs expire before the second-trigger is met and they're converted to full shares, employees will lose trust in their compensation.

But the IRS requires that RSUs carry substantial risk of forfeiture. What the company can't do is say "Don't worry, Susan, even if your $2M in RSUs expire we'll just give you $2M immediately in new ones that expire in 8 more years." A statement or practice like that would immediately throw up flags with the IRS.

The company would be signaling there isn't substantial risk of forfeiture. And if the IRS noticed, not only would they say that Susan owes taxes on the $2M because the company winked and nodded about her shares expiring but **every** employee with RSUs would owe taxes once their time-based trigger was met.

## The RSU Cookie Jar

Another way to think of it is like a giant, hermetically sealed cookie jar. The cookies in the jar represent the RSUs belonging to each and every employee. So long as the jar stays sealed, the IRS doesn't tax employees.

Some of the cookies though are due to expire, and those employees are sad. The dilemma is that if just one person were to extract their cookies or have their expired cookies replenished with a new one, the IRS consider the seal broken. Now all those employees are required to pay the cookie tax.

The company is responsible for withholding income tax from the RSUs that just failed to meet their risk forfeiture test. This could be problematic for a company with billions of dollars of employee income tax liability. Most non-public companies don't store those sort of cash reserves on hand for the purpose of paying employee taxes.

So what's a company to do?

## Stripe's Fundraise

Stripe faced this conundrum in early 2023. The company was about a year out from their first RSU expiration. Employees were restless to know what the company would do since the economy and market didn't seem to indicate that a public offering would be imminent. Would the company allow those first RSUs to expire? This would signal to remaining employees that the company may allow their RSUs, even with distant expirations, to become worthless too.

Stripe in this case decided to [raise](https://stripe.com/newsroom/news/stripe-series-i-employee-liquidity){:target="_blank"} a substantial sum of money. The fundraise was done in such a way as to satisfy the liquidity trigger requirement. In addition, enough funds were raised so that employees could sell as much of their now vested RSUs as they desired.

_The exact mechanism of meeting the liquidity requirement isn't clear. A brief, circular, and hand-wavy explanation was once provided along the lines of "It's somewhat complicated, but I'll just say that it was met."_

_Typical liquidity events are public offerings or acquisitions. I imagine the legal definition of an acquisition involves a transfer of control. Maybe on paper Stripe was "acquired" via a transfer of control to a shell company. I'm sure outside counsel earned their stripes (no pun intended)._

## 22% vs 37%

In Stripe's fundraise, they gave employees a choice of how much withholding they would observe. In order to simplify the administration, if you had <$1M in RSUs vesting you could choose for the company to withhold either 22% or 37% in federal taxes.

22% was the minimum withholding the IRS requires below $1M; 37% was the highest tax bracket at the time.

Employees now faced another choice. They were told they'd be able to tender (sell) as much of their stock as they wanted. The tax event and the tender offer were separated by over a month. Because of this, I felt there was some risk. What if the company hit the liquidity event and had cash for the taxes, but some adverse event (for example, a breach) occurred that caused the tender offer to be withdrawn before employees could sell their shares.

In addition, Stripe would apply this same withholding rate to all future RSU vesting events for the year. And no further employee tender events were planned.

Lest I end up in another tax man pickle where I chose 22% withholding but actually owed more and couldn't sell, I opted for the conservative route of 37%.

The added benefit of this is that with a federal marginal tax rate <37%, you are actually guaranteed a refund on your year end taxes. This essentially acts as tendering a small portion of your stock without actually being at the mercy of the company to plan a full tender event.

In the end, I tendered all my available shares. After already having seen the share value drop > 50% during my tenure, I preferred to index into the broader market. With more illiquid shares vesting over the next year; it was the right psychological move for me. If the price went down further, I'd feel good about selling. And if the price went up, I'd experience the gain on the future vests.

Win win.