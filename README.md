# multilingual_alignment
Alignment data for Berkeley FrameNet and FrameNet Brasil
In the file attached to this repo, you'll find the alignment between English and Brazilian Portuguese data in FrameNet.
For each alignment technique, there's and ID in the JSON.

The possible alignments are:

- Matching ID/Name (id: id_matching, name_matching): aligns frames based on their names and/or IDs.
- Matching Core FEs (id: core_fe_matching): Jaccard similarity of the core FEs names. This only works when the FEs on the other FN are in english.
- LU translations using WordNet en→[l2] (id: lu_wordnet): Percentage of matching LUs in the english frame. A matching LU is any LU that shares a synset in OMWN with any of the l2 frame LUs.
- Synset count en→[l2] (id: synset): Percentage of matching synsets in the english frame. The synsets of a frame are all synsets that its LUs belong to. A matching synset is a synset that has at least one LU in the english frame and one LU in the l2 frame.
- Synset count [l2]→en (id: synset_inv): Percentage of matching synsets in the l2 frame. 
- Average core FE name and definition MUSE similarities (id: muse_fe_match): Average similarity of all possible pairs of FEs between frames. The similarity of a pair is the the cosine similarity of the names multiplied by the cosine similarity of the definition in the MUSE vector space. This only works when the FEs on the other FN are in english.
- Matching core FE weighted by definition MUSE similarities (id: muse_exact_fe_match): Similar to Matching Core FEs, but instead of counting the intersection of FE names we sum the FE definition similarities of each pair.
- LU translations using MUSE (id: lu_muse_k_t): Percentage of matching LUs in the english frame. A matching LU is any LU that neighbors one of the l2 LUs in MUSE representation space. The neighborhood size (k) and minimum similarity (t) can be changed.
- MUSE LU centroid similarity (id: lu_mean_muse): Cosine similarity between the frames' LU centroids.
- MUSE definition centroid similarity (id: frame_def_muse): Cosine similarity between the average vector of the frames' definitions.

The json can be [downloaded from here{https://drive.google.com/open?id=1Xmprwe0SndaI9SUSkkvndwQY_Fro6qjm}], as a zip file.
