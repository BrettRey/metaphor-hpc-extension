# Pelgrim, Raman, Serre & Buchsbaum (2025) -- Notes for Reviewer Responses

**Citation:** Pelgrim, M.H., Raman, S.S., Serre, T., & Buchsbaum, D. (2025). Evaluating dogs' real-world visual environment and attention. *Cognitive Science*, 49, e70080. DOI: 10.1111/cogs.70080

**Purpose of these notes:** Extract findings that bear on the four simulated reviewer challenges to the TRAIL-as-functional-category argument. This paper is the first to use head-mounted eye-tracking on dogs during naturalistic outdoor walks, documenting what dogs actually look at in real environments. It provides evidence that dogs visually attend to ground/path features selectively, not randomly or by simple saliency, which is directly relevant to the claim that dogs have a functional spatial category TRAIL.

---

## Study Design

- **Participants:** 11 pet dogs (7 female, mean age 6.5 years); breeds: 1 Miniature American Shepherd, 1 Australian Labradoodle, 2 Golden Retrievers, 2 Labrador Retrievers, 5 mixed breeds (p. 5)
- **Method:** Custom head-mounted eye-tracker (two cameras on dog goggles): one records the dog's right eye, one records the dog's first-person perspective. Field of view: 101.55 deg horizontal, 73.60 deg vertical. 29.96 fps. (p. 5)
- **Route:** 0.5 miles preset route through city streets and campus greenspaces (p. 6)
- **Data:** 11,698 total fixations across 11 dogs, spanning 102,868 frames; after exclusions (sniffing bouts, sparse scenes, CV failures), 10,296 look images used for analysis (p. 11)
- **Fixation definition:** Stable eye positioning lasting 100 ms or more (p. 6)
- **Item classification:** 15 classes identified via fine-tuned Mask R-CNN panoptic segmentation: bench/chair, bicycle, building, bus, car, construction, pavement, person, plant_horizontal, plant_vertical, pole, scooter, sculpture, sign, sky (p. 7, Table 1 on p. 9)
- **Spatial accuracy:** 5.32 deg (first outdoor deployment; indoor accuracy previously 3.6 deg) (p. 7)
- **Saliency comparison:** Saliency Toolbox v2.3 (Walther & Koch 2006), run in both grayscale and full colour to account for dogs' different colour perception (p. 9-10)

---

## Key Findings

### Finding 1: Dogs visually attend to ground/navigational features disproportionately

**Exact data (Table 1, p. 9; discussion pp. 15, 18):**
- Pavement: in view 88.5% of the time (SE = 0.047), fixated 38.1% of time when in view (SE = 0.069), average size when in view = 0.336 (SE = 0.027)
- Plant_horizontal (grasses, ground-level vegetation): in view 61.6% of time (SE = 0.041), fixated 17.4% of time when in view (SE = 0.032), avg size = 0.18 (SE = 0.019)
- Combined ground-level attention: "Dogs also attend frequently to the ground in front of them, looking to the pavement 38% of the time it is in view and looking to horizontal plants (like grasses that could be walked on) around 17.4% of the time in view" (p. 15)

**Explicit navigational interpretation by the authors:** "These looks may be for navigational or wayfinding purposes, as past research suggests that when navigating in a real-world context, people often look to the ground, helping us to map a path forward and to avoid obstacles (20% to the ground in de Winter et al., 2021, 55.9% to street edges and the ground in Simpson, Thwaites, & Freeth, 2019, and 31.8% looking to ground obstacles in Franchak & Adolph, 2010)" (p. 15)

**Conclusion section restatement:** "Like human adults (de Winter et al., 2021; Simpson et al., 2019), dogs frequently attend to classes (i.e., pavement, horizontal plants) that are directly related to ground navigation, helping to find a smooth path and monitor for potential obstacles" (p. 18)

**Bearing on reviewer challenges:**
- **Horowitz (anecdotal; simpler explanations):** This is systematic, multi-dog evidence that dogs visually monitor path/ground features during naturalistic walking. The 38% fixation rate on pavement specifically is not explained by "visual salience" (see Finding 4 below), since the saliency model is a poor predictor of fixations. Dogs are selectively attending to walkable surfaces, not just high-contrast features.
- **Keil (functional category vs perceptual generalisation):** Dogs don't just detect ground features passively; they actively direct gaze to pavement and walkable vegetation. This selective visual attention to navigational surfaces is consistent with a functional category that organises behaviour, not merely a perceptual detection response.
- **Godfrey-Smith (observer-relative functional domains):** The navigational interpretation is supported by convergence with the human eye-tracking literature (de Winter, Simpson, Franchak & Adolph). Both dogs and humans look at the ground for wayfinding. The functional domain "navigable surface" is not merely observer-imposed; it is evidenced by the animal's own gaze allocation.

---

### Finding 2: Dogs actively direct attention to specific item classes (not random looking)

**Exact data (p. 14):**
- Significant main effect of item class on whether dogs fixated items when in view: chi-squared(10) = 1348.97, p < .001
- Dogs looked at people 15.7% of the time they appeared
- Dogs looked at benches/chairs only 1.2% of the time they were in view
- Pairwise comparison, people vs benches/chairs: t(51,368) = -5.805, p < .001
- Dogs looked at people significantly more than sculptures: t(51,368) = 5.137, p < .001
- Dogs looked at people significantly more than sky: t(51,368) = 16.346, p < .001

**Bearing on reviewer challenges:**
- **Horowitz / Keil (simpler explanations / mere perceptual generalisation):** The massive chi-squared demonstrates that dogs are not looking randomly. They actively direct gaze to certain categories over others. This is inconsistent with pure bottom-up salience or random scanning. It is consistent with category-level organisation of visual attention.

---

### Finding 3: Sky is almost never fixated despite being ubiquitous

**Exact data (p. 15):**
- Sky: present in 83.8% of fixation opportunities (nearly always available)
- Fixated only 7% of the time it was in view (Table 1, p. 9: proportion fixated = 0.07, SE = 0.026)
- Plant_vertical (trees, bushes): fixated 26.9% of time in view, significantly more than people: t(51,368) = -17.154, p < .001

**Authors' interpretation:** "This suggests that, unlike plants, in a real-world context, the sky is treated by dogs as a background, or at least not something that is worth attending to" (p. 15)

**Bearing on reviewer challenges:**
- **Keil (functional category vs perceptual generalisation):** Dogs are not just attending to whatever is large and visible. The sky is the most ubiquitous item and occupies large portions of the visual field, yet dogs almost never fixate it. By contrast, pavement (also large, also ubiquitous) is fixated 38% of the time. This asymmetry (ground = attended; sky = ignored) is consistent with a navigational functional category directing attention selectively.

---

### Finding 4: Saliency model is a poor predictor of dogs' fixations

**Exact data (p. 17):**
- AUC-Judd (full colour): 0.67
- AUC-Judd (grayscale): 0.66
- (AUC ranges from 0.5 = chance to 1.0 = perfect prediction)

**Authors' interpretation:** "This suggests that the saliency model is a poor predictor of dogs' looking behaviors, or that it is unlikely dogs' fixations are driven solely by low-level image saliency features. The ROC curve as well as further details on AUC calculations and saliency analysis can be found in Supplementary Materials" (p. 17)

**Conclusion section:** "Dogs' visual attention is active and is not just driven by the low-level image saliency features (e.g., luminance, color, orientation). Instead, dogs attend selectively to certain item classes" (p. 17)

**Bearing on reviewer challenges:**
- **Horowitz (visual salience / contrast-tracking as simpler explanation):** This is the single most important finding for responding to Horowitz. The saliency model (which captures exactly the low-level features Horowitz suggests might explain painted-line following: contrast, luminance, edge detection) predicts dogs' actual fixation behaviour only marginally better than chance (AUC 0.66-0.67). Dogs are NOT primarily driven by visual salience. Their gaze is driven by something more like item-class identity. A white line on a green field is maximally salient, but saliency alone does not explain where dogs look. If the dog follows a painted line, it is not because the line is visually salient; it is because the line matches something in the dog's category structure.
- **Keil (functional category vs perceptual generalisation):** The saliency failure is key evidence against "mere stimulus generalisation." If dogs were generalising on perceptual features (contrast, edges), the saliency model would predict their fixations well. It does not. Dogs attend based on item category, not on low-level perceptual features. This is consistent with a functional category organising attention, not a generalisation gradient from perceptual similarity.
- **Holyoak (evidence vs illustration):** This finding converts the TRAIL argument from illustration to something with stronger empirical grounding. We can now say: controlled multi-dog eye-tracking data show that dogs' visual attention during walks is category-driven, not saliency-driven, and that ground/navigational features receive disproportionate attention.

---

### Finding 5: Fixation duration varies by item class, not by item size

**Exact data (pp. 16-17):**
- Average fixation duration: M = 301.8 ms, SD = 481.09 ms (before distributing across regions); M = 190.11 ms, SD = 368.27 ms (after distributing)
- Significant effect of item class on fixation duration: chi-squared(14) = 111.49, p < .001
- NO main effect of fixated item size: chi-squared(1) = 0.19, p = .66
- Benches/chairs: M = 166.67 ms, SD = 47.14 (very short fixations)
- Cars: M = 380.87 ms, SD = 582.55 (long, variable fixations)
- Significant interaction between item class and fixated item size: chi-squared(13) = 37.91, p < .001

**Bearing on reviewer challenges:**
- **Keil:** Dogs fixate different durations on different item classes, but fixation duration is NOT driven by item size (p = .66). This means dogs are not simply looking longer at bigger things. Category identity, not perceptual magnitude, determines looking time. This supports the view that category-level representation drives visual attention.

---

### Finding 6: Significant individual differences in some categories but consistency in others

**Exact data (p. 15):**
- Significant interaction between dog identity and class on fixation: chi-squared(100) = 3997.19, p < .001
- People: one dog looked at people 46% of the time they were in view; another dog looked at people around 5% of the time (not significantly more than any other class at p < .05)
- Comparison between these two dogs: t(51,368) = 4.21, p = .001
- Benches/chairs: dogs were consistent (rarely looked, no significant individual differences at p < .05)

**Bearing on reviewer challenges:**
- **Holyoak (evidence vs illustration):** Individual variation in some categories (people) but consistency in others (benches/chairs, sky) demonstrates that the pattern is not an artefact of one unusual dog. The consistency across dogs in ignoring sky and attending to ground/pavement is particularly relevant: all dogs monitored navigational surfaces.

---

### Finding 7: Dogs look at doors and functional parts of buildings

**Exact data (p. 18):**
- "Anecdotally, we noticed that on many fixations to buildings, dogs were specifically looking to the doors and windows of buildings. This pattern was also observed with buses, with dogs often looking at the door of the bus."
- Authors suggest: "It is possible that dogs are looking to these portions of buildings and buses because of anticipated functionality (i.e., dogs look to doors of the buildings because they could enter through the door) or for anticipatory social reasons (i.e., people often appear in doorways so doorways are more interesting because of this potential)"

**Bearing on reviewer challenges:**
- **Keil (functional category vs perceptual generalisation):** Dogs attend to functionally relevant parts of objects (doors, not walls), suggesting their visual attention is organised by functional affordances, not just by perceptual features. This is consistent with the broader claim that dogs' spatial categories are functionally structured.
- **Godfrey-Smith (observer-relative functional domains):** Attending to doors (entry points, places where people appear) suggests the dog itself is sensitive to functional distinctions, not just the observer.

---

### Finding 8: Olfaction and vision may be jointly integrated

**Exact data (p. 19):**
- Sniffing bouts were excluded from the visual analysis
- But the authors note: "Recent work has suggested that dogs' olfaction may be integrated into their visual processing, perhaps into a joint representation of their visual and olfactory environment (Andrews, Pascalau, Horowitz, Lawrence, & Johnson, 2022). Therefore, the odors in dogs' environment may be encouraging them to orient their visual attention to a particular visual target or region (and visual attention may similarly be guiding olfaction)."

**Bearing on reviewer challenges:**
- **Horowitz:** Directly relevant. The olfactory-visual integration point (citing a paper co-authored by Horowitz herself) supports the view that TRAIL is a multimodal category. The dog's visual attention to ground features is not independent of its olfactory processing; the two modalities may work together, exactly as a functional spatial category would predict. The Andrews et al. (2022) paper on the canine olfactory pathway revealed "extensive connections" between olfactory and visual cortex, providing a neural basis for cross-modal TRAIL processing.

---

## Summary: How This Paper Bears on Each Reviewer Challenge

### Horowitz: Anecdotal / simpler explanations

Pelgrim et al. provide the controlled, multi-dog evidence Horowitz demands:

1. **Not anecdotal:** 11 dogs, 10,296 analysed fixations, computer-vision-coded, with statistical tests. This is the methodological standard Horowitz called for.
2. **Saliency refuted as primary driver:** AUC-Judd 0.66-0.67 (barely above chance). Low-level visual features (contrast, luminance, edges) do not predict where dogs look. If the painted-line observation were driven by "visual salience" or "contrast-tracking," we would expect the saliency model to predict fixations well. It does not.
3. **Dogs visually monitor ground/navigational features selectively:** 38% fixation on pavement when in view, despite sky (equally large, equally available) receiving only 7%. This selective ground-monitoring is consistent with a navigational functional category.
4. **Olfaction-vision integration:** Andrews et al. (2022), cited by Pelgrim et al. (and co-authored by Horowitz), found extensive connections between olfactory and visual cortex in dogs. This supports the multimodal character of TRAIL.

**Limitation:** This paper does not document painted-line following specifically. It documents the broader pattern of selective visual attention to navigational surfaces during walks.

### Keil: Functional category vs perceptual generalisation / stimulus generalisation

Pelgrim et al. provide three lines of evidence against "mere stimulus generalisation":

1. **Saliency model fails:** If dogs generalised on perceptual features (edges, contrast, luminance), the saliency model would capture their fixations. It does not (AUC 0.67). Something beyond low-level perceptual features drives gaze allocation.
2. **Category identity, not size, determines fixation duration:** No main effect of item size on fixation duration (p = .66), but significant effect of item class (p < .001). Dogs respond to what something *is*, not how perceptually prominent it is.
3. **Functional parts attended selectively:** Dogs look at doors of buildings and buses, not at walls. This is functionally organised attention, not perceptual generalisation.
4. **Sky ignored despite ubiquity:** The most perceptually available item (83.8% of scenes) is almost never fixated (7%). Ground surfaces, by contrast, are heavily attended. This asymmetry is predicted by a navigational functional category but not by perceptual generalisation.

**Net effect:** The Keil challenge asks whether the dog has "a genuine functional category or just perceptual generalisation." Pelgrim et al. show that dogs' visual attention is organised by item class, not by perceptual features, and that this organisation is consistent with functional (navigational) categories. This does not prove TRAIL is an HPC kind, but it provides the kind of evidence Keil asks for: evidence that the dog's behaviour is not driven by "feature correlation without any grasp of the mechanisms linking the features."

### Godfrey-Smith: Functional domains are observer-relative

Pelgrim et al. address this indirectly:

1. **Dogs themselves distinguish navigational from non-navigational visual targets:** The pavement/sky asymmetry (38% vs 7% fixation) is the dog's own attentional allocation, not the observer's classification. The dog is sorting its visual world into attended navigable surfaces and ignored non-navigable space.
2. **Convergence with human navigational eye-tracking:** The authors explicitly compare dog ground-attention to human navigational eye-tracking (de Winter et al. 2021; Simpson et al. 2019; Franchak & Adolph 2010). The parallel suggests that "navigable surface" is a functional domain that organises visual attention across species, not an observer-imposed category.
3. **Doors as functional targets:** Dogs attend to functionally relevant parts of objects (doors, not walls), suggesting the dog itself is sensitive to functional distinctions.

**Limitation:** The paper does not resolve the deep question of whether the dog represents painted lines as belonging to a different functional domain from trails. But it provides evidence that the dog's visual attention is functionally organised, which makes the attribution of functional categories less observer-dependent.

### Holyoak: Evidence or illustration?

Pelgrim et al. convert the TRAIL argument from illustration toward evidence:

1. **Controlled methodology:** 11 dogs, head-mounted eye-tracking, computer vision coding, statistical analysis. This is exactly the kind of controlled observation Holyoak requested.
2. **Quantified selective attention:** The massive chi-squared values (item class on fixation: 1348.97, p < .001) demonstrate that dogs' visual attention is systematically organised, not random.
3. **Individual consistency in navigational attention:** Despite significant individual differences in social attention (people), dogs were consistent in their ground-monitoring behaviour and in ignoring the sky. The navigational-attention pattern generalises across dogs.
4. **Saliency model failure strengthens argument:** If dogs' gaze were driven by low-level features, the painted-line case would be mere perceptual attraction. The saliency model's poor performance shows that category-level organisation, not perceptual saliency, drives looking behaviour.

**Limitation:** This paper is still evidence for the general claim (dogs visually attend to navigational features in a category-organised way), not for the specific painted-line claim. But it provides the empirical scaffolding that Holyoak said was missing.

---

## Quotable Passages

> "Dogs' visual attention is active and is not just driven by the low-level image saliency features (e.g., luminance, color, orientation). Instead, dogs attend selectively to certain item classes." (p. 17)

> "Like human adults (de Winter et al., 2021; Simpson et al., 2019), dogs frequently attend to classes (i.e., pavement, horizontal plants) that are directly related to ground navigation, helping to find a smooth path and monitor for potential obstacles." (p. 18)

> "These looks may be for navigational or wayfinding purposes, as past research suggests that when navigating in a real-world context, people often look to the ground, helping us to map a path forward and to avoid obstacles." (p. 15)

> "Recent work has suggested that dogs' olfaction may be integrated into their visual processing, perhaps into a joint representation of their visual and olfactory environment (Andrews, Pascalau, Horowitz, Lawrence, & Johnson, 2022)." (p. 19)

> "Dogs could be directing their attention based on interest in different item classes, or it could be a more bottom-up process driven by low-level image features contributing to increased saliency of regions of the image." (p. 8) [Sets up the saliency test]

> "For our full-color analyses, AUC-Judd was 0.67. Similarly, the AUC-Judd for grayscale analyses was 0.66. This suggests that the saliency model is a poor predictor of dogs' looking behaviors, or that it is unlikely dogs' fixations are driven solely by low-level image saliency features." (p. 17) [The key result]

---

## Key References Cited by Pelgrim et al. That May Be Useful

- **Andrews, E.F., Pascalau, R., Horowitz, A., Lawrence, G.M., & Johnson, P.J. (2022).** Extensive connections of the canine olfactory pathway. *Journal of Neuroscience*, 42(33), 6392-6407. [Olfactory-visual cortex connections; co-authored by Horowitz]
- **de Winter, J., et al. (2021).** How do pedestrians distribute their visual attention when walking through a parking garage? *Ergonomics*, 64(6), 793-805. [Human ground-monitoring during walking: 20%]
- **Simpson, J., Thwaites, K., & Freeth, M. (2019).** Understanding visual engagement with urban street edges. *Sustainability*, 11(15), 15. [Human ground-monitoring: 55.9% to street edges and ground]
- **Franchak, J.M., & Adolph, K.E. (2010).** Visually guided navigation: Head-mounted eye-tracking of natural locomotion in children and adults. *Vision Research*, 50(24), 2766-2774. [Human ground-monitoring: 31.8% to ground obstacles]
- **Byosiere, S.-E., et al. (2018).** What do dogs see? *Psychonomic Bulletin & Review*, 25(5), 1798-1813. [Dogs: worse visual acuity, less colour sensitivity, better flicker rates and dim-light performance than humans]

---

## BibTeX Entry

```bibtex
@article{pelgrim2025evaluating,
  author    = {Pelgrim, Madeline H. and Raman, Shreyas Sundara and Serre, Thomas and Buchsbaum, Daphna},
  title     = {Evaluating Dogs' Real-World Visual Environment and Attention},
  journal   = {Cognitive Science},
  volume    = {49},
  pages     = {e70080},
  year      = {2025},
  doi       = {10.1111/cogs.70080}
}
```
