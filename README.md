# Unique Search Proof of Concept

How can we search for more unique information? 

What if we:
- compare potential new pages to pages we've already read
- choose pages that have new content or "new meaning" relative to the current page
- link pages based on semantic meaning instead of just hyperlink hrefs?
(This is deliberately vague. Let's build up to it.)

Then we'll need:
- pages linked to other pages, or a hypertext graph, which means we need to crawl the Internet
- seed pages to crawl, ideally larged and already tagged with rich metadata for building models of meaning
- statistical models of meaning, so some form of machine learning that is not too hard to implement and tune

Let's decide on a stack for quick debugging:
- backend
    - Jupyter notebooks running Python 3.6+
    - we'll be running long I/O and CPU jobs for both 
web crawling and model training we'll want to split the notebooks so that we can capture and store output from 
each step on disk
    - use caching for reproducibility
    - can also run a REST API to debug server-side model inference
- frontend
    - browser-based
    - visualize hypertext graphs
    - show pages and their relative similarities
    - compare pages via potential on-demand crawling
    - d3js (and HTML, CSS)
- infrastructure
    - CPU
        - Azure notebooks
        - local Docker
    - Storage
        - CSV and JSON
        - local to Azure instance
        - local machine
