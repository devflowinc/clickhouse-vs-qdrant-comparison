<p align="center">
  <img height="100" src="https://raw.githubusercontent.com/arguflow/blog/5ef439020707b0e27bf901c8f6b4fb1f487a78d4/apps/frontend/public/assets/horizontal-logo.svg" alt="Arguflow">
</p>

<p align="center">
    <b>Offering a product suite for putting arbitrary models into production semantic search and retrieval-augmented LLM-chat experiences on your company's data</b>
</p>

<p align="center">
<strong><a href="https://docs.arguflow.ai">Documentation</a> • <a href="https://search.arguflow.ai">Competitive Debate Search Demo</a> • <a href="https://chat.arguflow.ai">Competitive Debate Chat Demo</a> • <a href="https://discord.gg/CuJVfgZf54">Discord</a>

</strong>
</p>

# Exploring replacing our SVD (qdrant) with Clickhouse

The objective behind this notebook was to assess the feasibility of substituting our system's SVD (specialized vector database), [Qdrant](https://qdrant.tech/), with [Clickhouse](https://clickhouse.com/). Employing ClickHouse would offer the advantage of utilizing a comprehensive DBMS, thereby eliminating the need for external database joins during diverse search operations.

## Findings

The key takeaway here is that we are strategically developing our systems to facilitate seamless replacement of the underlying vector store. Anticipating the uncertain trajectory of vector store solutions, we're exercising caution and refraining from fully committing to any particular data store solution at this point.

For now, we will stick to [Qdrant](https://qdrant.tech/) for our competitive debate demos as [Clickhouse](https://clickhouse.com/)'s [annoy index](https://clickhouse.com/docs/en/engines/table-engines/mergetree-family/annindexes) is too imprecise to be viable.

However, it is important to note that Clickhouse wins out on pure speed and can be the right choice for datasets characterized by substantial sparsity or considerable size. We may use Clickhouse for future customer deployments when it makes sense to do so.

## Replicating our results

Head over to [this repository's notebook](https://github.com/arguflow/qdrant-clickhouse-migrator/blob/main/qdrant-to-ch.ipynb) and follow the instructions there.
