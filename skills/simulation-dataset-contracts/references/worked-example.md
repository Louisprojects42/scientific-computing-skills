# Example contract decisions

A record declares schema_version, domain_id, geometry_id, lineage_group, case_id, recipe_id, field conventions, provenance, status, and artifact references. This is an illustrative field set, not a prescribed schema.

A pressure field must distinguish absolute pressure, gauge pressure, pressure divided by density, and coefficient form. Name, units, reference pressure, density, reference velocity, and coordinate convention determine interpretation; array shape alone does not.

Compatibility examples:

- Optional diagnostic field with a documented default may be additive if existing readers tolerate new fields.
- Changing a lift sign or reference area changes meaning even if the JSON type is unchanged.
- Allowing null in a schema while a runtime model rejects it is contract drift.
- Two remeshes of one shape belong to the same leakage group; split them together.
- Mixing solver recipes needs explicit labeling and evaluation by recipe, or separate datasets.

Verify the chosen JSON Schema dialect and implementation with the target consumer. Leave any unresolved interoperability decision visible.
