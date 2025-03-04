# Medical-KET-RAG

Implemented the Case
ICU physician hands off a case ("Investigate Meropenem failure for Patient X and recent sepsis cohort") to a KET-RAG sandbox, which pulls the latest articles (e.g., PubMed), patient data (Chronicles), and hospital trends (Clarity/Caboodle) to generate an enriched test case suggesting an alternative antibiotic (e.g., Colistin) within 4 hours.<br>

Success Criteria:<br>
<br>
Generates a test case with preconditions, steps, and outcomes reflecting resistance insights. Incorporates a mock article (e.g., "Colistin for NDM-1 resistance"). Delivers results via a simulated Clarity report, avoiding real-time disruption. Stays under 300 lines, with comments and outputs.<br>

Key Components Physician Handoff: Simulated via physician_handoff(), mimics an ICU physician submitting a case through Epic Clarity.
Data Pull:
Mock CHUNKS includes patient data (Chronicles), trends (Caboodle), and a recent article (PubMed), reflecting the handoff’s scope.
Ranking (Layer 1):
simulate_pagerank() prioritizes resistance-related chunks (e.g., article, patient data), building a sparse graph.
Keyword-Chunk Graph (Layer 2):
query_keyword_graph() links "resistance" to chunks, extracting "Colistin" as an alternative.
Test Case Generation:
mock_llm() creates a detailed test case with article-driven insight (e.g., "Switch to Colistin").
Delivery:
Results delivered as a simulated Clarity report 4 hours later (e.g., 12:00).
Value Highlights
Printed at each stage to show KET-RAG’s contribution (e.g., cost reduction, actionable insights).
