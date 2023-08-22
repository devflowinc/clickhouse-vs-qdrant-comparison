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

# Can Clickhouse replace a SVD (qdrant)?

The purpose of this repository was to evaluate replacing our system's SVD, qdrant, with Clickhouse. It would be convenient to use Clickhouse as it is a full DBMS and would allow us to avoid executing external db joins when performing various search operations.

## Findings

The most important thing to note is that we are building out our systems such that it is easy to replace the vector store that is being used under the hood. It is difficult to predict how vector store solutions will evolve, and we are not yet willing to bet the house on any single data store.

For now, we will stick to [Qdrant](https://qdrant.tech/) for our competitive debate demos as [Clickhouse](https://clickhouse.com/)'s [annoy index](https://clickhouse.com/docs/en/engines/table-engines/mergetree-family/annindexes) is too innacurate to be viable.

However, it is important to note that clickhouse wins out on pure speed and can be the right choice for datasets which are very sparse or large. We may use Clickhouse for future customer deployments when it makes sense to do so.

## Replicating our results

Head over to [this repository's notebook](https://github.com/arguflow/qdrant-clickhouse-migrator/blob/main/qdrant-to-ch.ipynb) and follow the instructions there.
