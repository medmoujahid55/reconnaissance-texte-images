<h2>Facial Recognition & Detection : example OpenCV with Tesseract (OCR)<h2>

# INTRODUCTION OpenCV  Tesseract

  - Open Source OCR engine sponsored by Google since 2006.
  - Originally developed by HP between 1985-1994
  
# TessOCR Architecture
  
  <img src="/images/archi1.png" alt="Logo">


# Space betwwen word are  tricky TOO

  - Italics, digits, punctuation all create special-case font-dependent spacing.
  - Fuly justiified text in narrow columns can have vastly varying spacing on diffrent lines. 

  <img src="/images/sc2.png" alt="Logo">
  
 # Tesseract Word Recognizer 
 
   <img src="/images/sc3.png" alt="Logo">

 # Outline Approximation
 
  - Polygonal appromaximation is a double-edged swrod.
  - Noise and some pertinent information are both lost.
  
   <img src="/images/sc4.png" alt="Logo">

# Why it's called Tesseract?
 
  - Elements of polygonal approximation, clustered within a character/font combination.
  - x, y position, direction, and length (as a multiple of feature length).
  
   <img src="/images/sc6.png" alt="Logo">
   
# Character Classifier (Features and Matching)?
 
  - Static classifier uses outline fragments as features, broken characters are easily recognizable by small->large matching process in classifier. (this is slow).
  - Adaptive classifier uses the same technique.
  
   <img src="/images/sc5.png" alt="Logo">

# Classifier as Histogram of Gradients
 
  - Quantize character area.
  - Compute gradient within.
  - Histograms of gradients map fixed dimension feature vector.
  
   <img src="/images/cs7.png" alt="Logo">
   
 # Character Segmentation
 
  - segmentation Graphs.
  
   <img src="/images/sc7.png" alt="Logo">
   
 # Rating and Certianly
 
  - Rating = distance * outline length
    * Total rating over a world (or line if you prefer) is normalized
    * Different length transcriptions are fairly comparable
 
  - Certainly = -20 * Distance
    * Measures the absolute classification confidence
    * Surrogante for log probablity and is used to decide what needs more work
   
# Tesseract Training
   <img src="/images/sc8.png" alt="Logo">


