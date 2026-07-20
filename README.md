# FreshCount-V2-

"I gathered user feedback from a fast-paced restaurant environment. Recognizing tech-literacy barriers in users in their 60s and high inventory turnover, I pivoted the architecture from a passive tracker to an active, low-friction digital procurement tool, reducing ordering administrative overhead for the business owner."

Restaurant supplier ordering platform, refactoring V1 inventory tracker into a Spring Boot + MySQL system that routes orders to multiple wholesalers

i will be moving FreshCount from a snanner system, rather than just displayig the item list, whatever the command was, it will now act as a reordering system which can place the orderers for the business owner, essencially a supplier ordering platform or restaurants.

This will be specifically built for my a HaoWei. v1 was validated in production by the owner, he confirmed the system worked correctly but pointed out that their 1-2 week stock turnover made tracking redundent, the real bottleneck was identified by me as the time spent placing weekly orders across multiple wholesaler. v2 addresses that directly

update i will not be doing any of that^^

after careful thought, v1 was the right direction and refactoring into v2 doesnt fit this case, at least this specific v2

instead v2 will be:

Display the current stock, low stock etc..
there will be another page for the restock, this is where you input the number 
or click the item then it adds it to the pdf for that supplier, 
the pdf generated can use the specific SKU from that supplier for those specific items

this means the database would have to change so that the SKU links with the direct supplier

sequence:
1. Staff/owner completes stocktake
2. FreshCount checks low-stock items
3. System groups items by preferred supplier
4. Owner reviews the order
5. Owner can override supplier if needed
6. System confirms restock order
7. FreshCount generates one PDF per supplier
8. PDFs can be printed, emailed, or saved
9. When delivery arrives, stock quantities are updated

10. Stocktake / stock levels
        ↓
Low-stock detection
        ↓
Restock basket
        ↓
Preferred supplier grouping
        ↓
Owner review + supplier override
        ↓
Confirm restock order
        ↓
Generate separate supplier PDFs
        ↓
Delivery arrives
        ↓
Update stock movements
