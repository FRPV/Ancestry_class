Es recomendable crear una carpeta para la clase. En esta descargar RFMIx y el pipeline de Ancestria

```console
#Ingresamos al directorio donde fue descargado RFMix

cd RFMix_v1.5.4/


#Descargamos el archivo con datos input y descomprimimos

wget https://raw.githubusercontent.com/FRPV/Ancestry_class/master/datos/NA19755_aux-results.zip

wget https://raw.githubusercontent.com/FRPV/Ancestry_class/master/datos/NA19755_input.zip

unzip NA19755_aux-results.zip

unzip NA19755_input.zip

#Creamos la carpeta donde se depositaran los resultados

mkdir NA19755_results/

#Ejecutamos RFMix en el cromosoma 1

python RunRFMix.py PopPhased NA19755_input/haps_chr1 NA19755_input/Pop-clases.txt NA19755_input/Markers_chr1.txt --forward-backward -o NA19755_results/NA19755_chr1

#Ejecutamos RFMix en el cromosoma 2

python RunRFMix.py PopPhased NA19755_input/haps_chr2 NA19755_input/Pop-clases.txt NA19755_input/Markers_chr2.txt --forward-backward -o NA19755_results/NA19755_chr2


#Copiamos los archivos auxiliares en la carpeta de resultados

cp NA19755_aux-results/NA19755_chr* NA19755_results/



#Regresamos un directorio arriba

cd ..


#Colapsamos los resultados de RFMix en archivos de intervalos

python ancestry_pipeline/collapse_ancestry.py --rfmix RFMix_v1.5.4/NA19755_results/NA19755_chr1.0.Viterbi.txt --snp_locations RFMix_v1.5.4/NA19755_input/Markers_chr1.txt --fbk RFMix_v1.5.4/NA19755_results/NA19755_chr1.0.ForwardBackward.txt --fbk_threshold  0.85 --ind NA19755 --ind_info RFMix_v1.5.4/NA19755_input/sample_name --pop_labels NAT,YRI,CEU --out RFMix_v1.5.4/NA19755_results/NA19755

#Copiamos el archivo de centromeros en el directorio actual
cp ancestry_pipeline/centromeres_hg19.bed .


#Colapsamos los resultados de RFMix en archivos de intervalos

python ancestry_pipeline/plot_karyogram.py --bed_a RFMix_v1.5.4/NA19755_results/NA19755_A.bed --bed_b RFMix_v1.5.4/NA19755_results/NA19755_B.bed --ind NA19755 --pop_order NAT,YRI,CEU --out NA19755_RFmix.png
```
