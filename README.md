# Building the Specimen

**An atlas in progress of sodium pentobarbital, prepared around the ERC project MORTALMED.**

This repository is called `mortalmed-mexico` because it began as preparation for MORTALMED's Mexico subproject. It now also holds early work on Switzerland and on a possible Spanish fieldsite. The name stays for now, so existing links keep working.

Santiago Orrego · urban anthropologist and STS scholar · [sorregoxyz.github.io](https://sorregoxyz.github.io)

## What this is

MORTALMED (*Mortal Medicine: The Social Life of a Death-Inducing Pharmaceutical*) is an ERC Starting Grant led by Dr Marcos Freire de Andrade Neves at the University of Glasgow. It follows sodium pentobarbital as a *pharmakon*, remedy and poison at once, through the *necro-socialities* where death is managed, authorised and contested.

**Building the Specimen** is my own preparatory work around that project: a cartography of pentobarbital's actors and relations, and a set of field diaries that record how the cartography was built. The method extends the cartography of controversies I used on the African swine fever outbreak in Catalonia, and it borrows from specimenography: the drug is assembled, fragment by fragment, into a specimen that holds its many lives side by side rather than resolving them into one account.

### This is a thinking device, not a work plan, and not an official project output. Any subproject's design, sites, authorship and outputs belong to the PI and the team. The project's own mapping of pentobarbital's global circulation belongs to the PharmaFlows PhD.

## Three sites, three lives of the drug

| Site | Status here | The drug's life | Field diary |
|---|---|---|---|
| **Mexico** | State of the art, v0.1.0 (Oct 2026) | Circulation: veterinary markets, over the counter, across the border | [`field diary/Mexico`](field%20diary/Mexico/README.md) · 17 entries |
| **Switzerland** | First exploration (Nov 2026) | Prescription: the narcotics regime as the door to assisted suicide | [`field diary/Switzerland`](field%20diary/Switzerland/README.md) · 5 entries |
| **Spain** | First exploration, possible fieldsite (Nov 2026) | Afterlife: compounded for humans, industrial for animals, persistent in carcasses, soil and water | [`field diary/Spain`](field%20diary/Spain/README.md) · 6 entries |

MORTALMED's fourth context, lethal injection in the United States, appears here only through the literature and cases already in the data.

- **Mexico** prepared the application to the Mexico subproject: two main sites (Mexico City and Guadalajara) and Tijuana as a third-site candidate.
- **Switzerland** prepares the Research Associate post on *Lethal Prescriptions: Sodium Pentobarbital and Assisted Dying in Switzerland*, with fieldwork in Basel.
- **Spain** explores a possible new fieldsite, conditional on ERC approval. It is framed more-than-human and still speaks to human death: Barcelona as urban hub, Navarra or Asturias as rural site.

## How to read it

- **The maps** are force-directed graphs of entries and relations, with a register of entries and the field sites: one map per site, linked by a site menu. `index.html` covers **Mexico**; `switzerland.html` covers **Switzerland**. A Spain map and a small view of the connections between sites are planned.
- **The field diaries** (`field diary/<site>/`) are dated entries, each with *What I did*, *What I found* or *What I noticed*, *Open questions* and *Traces* (sources). Each folder has its own README index. Links use `[[wiki-link]]` syntax, so they read best in Obsidian.

## Running the map

The page reads the CSV files at load time, so it needs a local server; opening the file directly will not work.

```bash
cd mortalmed-mexico
python3 -m http.server 8000
# then open http://localhost:8000
```

VS Code's Live Server also works (see Mexico entry 11 for why the page needs a full document structure). The graph library is bundled in `data/d3.min.js`, so the map works offline.

## Data model

| File | Rows | Contents |
|---|---|---|
| `data/entries.csv` | 48 (Mexico) | Actors, documents, laws, cases and literature: `id, label, short, category, enactments, to_verify, description, verification_note, source, url` |
| `data/relations.csv` | 96 (Mexico) | Links between entries, typed by `circulation` |
| `data/sites.csv` | 3 (Mexico) | Candidate field sites, with reasons and considerations |

- **Categories:** `regulatory`, `clinical`, `advocacy`, `literature`.
- **Enactments**, the cross-cutting lens filter: `licensed`, `legible`, `desired`, `material`, `contested`, plus `frame` for conceptual entries. An entry can carry several. Contested is not a separate life of the drug; it runs through all of them.
- **Switzerland** uses the same model in `data/ch/`: 41 entries, 70 relations, 4 sites (Basel and Basel-Landschaft as the field site, Zurich and Solothurn as comparisons).
- **Circulations:** `institutional`, `material`, `informational`, `scholarly`.
- **Verification:** entries flagged `to_verify` carry a note on what still needs checking.

## Sources and ethics

- Everything here comes from desk research on public sources: laws, regulators' notes, court rulings, official statistics, peer-reviewed studies and press. Each diary entry lists its traces.
- The material stays at the institutional, legal, academic and discursive register. It deliberately does not document vendors, acquisition routes or doses. Illicit circulation appears only as public discourse.
- Nothing has been checked in the field yet. People and organisations named are public actors or appear as reported in public sources.

## Versions

- `v0.1.0-state-of-the-art-1`: Mexico cartography and field diary (October 2026).
- `v0.2.0-spain-exploration-1`: Spain field diary (November 2026).
- `v0.3.0-switzerland-exploration-1`: Switzerland field diary (November 2026).

## Repository layout

```
.
├── index.html            # Mexico map
├── switzerland.html      # Switzerland map
├── data/
│   ├── entries.csv
│   ├── relations.csv
│   ├── sites.csv
│   ├── d3.min.js
│   └── ch/               # Switzerland data (same columns)
└── field diary/
    ├── Mexico/           # 17 entries + README
    ├── Switzerland/      # 5 entries + README
    └── Spain/            # 6 entries + README
```
