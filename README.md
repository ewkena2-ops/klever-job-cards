# Klever job cards

The shop's printed paperwork, and a page that prints it.

**Live: https://ewkena2-ops.github.io/klever-job-cards/**

Pick the salesperson and the designer, choose A4 (one card) or A6 (four to a
sheet), print. Colour runs down the **left edge for the salesperson** and the
**right edge for the designer**, so a card says whose job it is without being
read. Each salesperson and designer shows with their photo, ringed in their
card colour; new people can be added on the page.

On A6 the **four cards are set up one at a time** — a sheet of four is four
jobs, not one job's stack. Choose the card in the rail, or click it on the
sheet, then set its two names. **Same on all 4** copies one card across when
the sheet really is one person's stack.

Print at **100% / actual size**. On A6, cut once across and once down.

## What is here

| | |
|---|---|
| `index.html` | the page above — the job card, printed to order |
| `print/Klever_Job_Card.*` | Form JC-01, the signing card, A4 |
| `print/Klever_Job_Card_Small.*` | Form JC-01S, the same card at A6, four to a sheet |
| | `?s=` and `?d=` take one name, or four comma-separated — one per card |
| `print/Klever_Job_Card_{Bruktawit,Tsega}.pdf` | JC-01 in each salesperson's colour |
| `print/Klever_Job_Flow_Card.*` | Form JF-01, the reading copy: who signs, in what order |
| `print/Klever_Job_Board_Cabinet.html` | the board cabinet |
| `print/Klever_Kanban_Board_Labels.*` | the wall labels, one tag per stage, six to an A4 |

## The rule that governs all of it

**The job card is the source of truth.** It defines the sixteen stages and who
moves each one; the cabinet, the wall labels and the page above all quote it
verbatim. Change the card first, then bring the rest into line.

The PDFs are printed from the HTML beside them with headless Chrome — edit the
HTML, never the PDF:

    chrome --headless=new --no-pdf-header-footer \
           --print-to-pdf=Klever_Job_Card.pdf Klever_Job_Card.html

## Hard stops — non-negotiable

* No production starts without 100% final payment confirmed by Selam and logged in the Job File.
* No delivery without QC release signed by Wede.
* No assembler payment without the physical Customer Acceptance Form in the Job File.
