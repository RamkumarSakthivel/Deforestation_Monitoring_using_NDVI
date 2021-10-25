# Deforestation_Monitoring_using_NDVI

NDVI approach is used to localise deforested areas because of the following reasons,
1. Healthy vegetation like forest, reflects near infrared really well and absorbs red light for photosynthesis.
2. Dying vegetation absorbs NIR and reflects red light.

Steps to compare two sets of sentinel-2 data to monitor deforestation:
1. Download the data for a selected region from Sentinel Hub.
2. Load the red(band4), green(band3), blue(band2) and nir(band8) images, in the form of arrays.
3. Slice the high resolution image arrays into smaller patches to reduce computation power and memory.
4. Normalise and stack red, green and blue patches to form true color composite.
5. Generate NDVI image by calculating the NDVI value using nir and red band image arrays.
6. Apply a threshold on NDVI image and create NDVI mask to differentiate forest and non-forest areas.
7. Repeat steps 1 to 7 on another set of data of the same region that has a different timestamp.
8. Visually compare the true color composite and NDVI mask of the corresponding sliced patches from both the data sets.
9. Calculate the total area deforested in the particular patch by comparing the pixels of both the data sets.
10. Save all the true color and ndvi mask patches to create GIFs if needed.