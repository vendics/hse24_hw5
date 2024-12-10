# hse24_hw5

# Часть 1
В первой части данной работы мы проводим анализ данных single cell RNA секвенирования. Данный анализ может быть полезен для кластеризации клеток по их экспрессии генов.

На входе у нас counts из датасета https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE103967 для клеток CD45- EpCAM+
Данное исследование проводилось на геноме мыши и чтения картировались на mm9

Код выполнения работы: (https://colab.research.google.com/drive/1LvKYeefihC7YJ_I18ofZ2DUtCjY-fQxA?usp=sharing)

После загрузки данных мы объединили их в одну таблицу. Затем провели нормализацию с использованием метода TPM. Этот метод был выбран, поскольку он лучше подходит для сравнения экспрессии между разными образцами, а не только между генами внутри одного образца. Для расчёта TPM сначала выполняется нормализация на длину гена, а затем на сумму всех значений, скорректированных по длине гена, в каждой клетке.
После нормировки построим heatmap

![image](https://github.com/user-attachments/assets/89b240ad-b8a6-4c33-975c-0faa6ac7b1ed)

Так как сортировка ещё не была проведена, на heatmap плохо видно различные группы клеток

Чтобы лучше увидеть кластеры построим UMAP и PCA
![image](https://github.com/user-attachments/assets/b526827d-ae4b-4d1c-8412-e8990de7ba7a)
![image](https://github.com/user-attachments/assets/d6472c6f-2ef6-4f9f-b231-8ac6b1bd85e2)

Вывод: на графиках отчётливо видны кластеры клеток с разной экспрессией генов что говорит о их функциональном различии


# Часть 2

Во второй части работы мы сравнивем уровни экспресси подгруппы клеток mTEC-IV из прошлой части с bulk RNA-seq для целого тимуса мыши из статьи [Meredith et al, 2015](https://pubmed.ncbi.nlm.nih.gov/26237550/)https://pubmed.ncbi.nlm.nih.gov/26237550/

![image](https://github.com/user-attachments/assets/1a09e7c1-042f-4e7e-a4e9-2b1319e0467d)
Гены, слабо эĸспрессирующиеся в "mTEC-IV", но высоĸо
эĸспрессирующиеся в "bulk", могут быть более универсальными или
хараĸтерными для других типов ĸлетоĸ

![image](https://github.com/user-attachments/assets/e6ba94d2-ff1b-4621-9a08-3fb91abb7493)

Вывод: как видно из графиков многие гены близки по экспресии, но где-то половина всё же значительно отличается. Это говорит о различии образцов bulk и single cell RNA-seq

