### Standardul folosit in codul C++ va fi trecut aici.  
Forma va fi: \<element\>: \<sintaxa\>    

Clasa: ClasaMea  
Variabila membra: mVariabilaClasei  
Variabila simpla: varibilaLocalaGlobala  
Constanta: VALOARE_CONSTANTA  
Directiva preprocesor: DIRECTIVA_PREPROCESOR  
Namespace: nume_spatiu  
Structura: StructuraMea  

Exemplu:  

```
//Fereastra.h

#ifndef FEREASTRA_H
#define FEREASTRA_H

SetariDeBaza {
    const int mLatime = 600,  
    mInaltime = 300;  
    const QString mNumeFereastra = "Aplicatia Mea";   
    bool mVizibil = true;
};

class Fereastra : public QMainWindow {
    Q_OBJECT
    Q_PROPERTY(int latime READ latime WRITE setLatime NOTIFY latimeSchimbat)
    bool mLatime;
protected:    
public:
    explicit Fereastra(QWidget *parent = nullptr);
    bool latime() const;
    void setLatime(const int &latime);
private slots:
protected slots:
public slots:
signals:
    void latimeSchimbat();
}
#endif // FEREASTRA_H

//Fereastra.cpp

Fereastra::Fereastra(QWidget *parent) : QMainWindow(parent),
    mLatime(0) {
    SetariDeBaza setari;
    mLatime = setari.mLatime;
    setMinimumWidth(mLatime);
    setMinimumHeight(setari.mInaltime);
    setWindowTitle(setari.mNumeFereastra);
    setVisible(setari.mVizibil);
}

bool Fereastra::latime() const {
    return mLatime;
}

void Fereastra::setLatime(const int &latime) {
    if (mLatime != latime) {
        mLatime = latime;
        //Aplica modificari necesare datei membre mLatime
        if (mLatime == 0) {
            SetariDeBaza setari;
            mLatime = setari.mLatime;
        }
        emit latimeSchimbat();
    }
}
```
