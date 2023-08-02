
Die Physische Schicht definiert die Spezifikationen für die Aktivierung, Aufrechterhaltung und Deaktivierung der physischen Verbindungen zwischen Endsystemen
- Elektrisch
- Mechanisch
- Verfahrenstechnisch(Kodierung, Synchronisation)
- Funktional (Datenrate, Entfernungen)

## Übertragungsmedien

Geleitete Medien:
- Coaxial Kabel
- Verdrilltes Kabel
- Glasfaserkabel

Ungeleitete Medien
- Radiowellen
- Mikrowellen
- Hochfrequenz-Radiowellen
- Lichtwellen


### Verdrilltes Kabel

Ein Verdrilltes Kabel besteht aus zwei isolierten Kupferkabeln. Diese werden verdrillt da zwei Parallele Kabel eine Antenne bilden

### Glasfaser

Ein Optischen Übertragungssystem hat drei Kern Komponenten:

- Eine Lichtquelle
- Ein Übertragungsmedium
- Einen Sensor

### Kabellose Übertragung

Die Empfangs stärke ist Proportional zu $\frac{1}{d^2}$ wobei $d$ die Entfernung zwischen Sender und Empfänger ist.

Das Empfangen von Signalen kann zusätzlich durch folgende Dinge Beeinflusst werden:

- Fading: Schwankung der Signalstärke aufgrund von Interferenzen und Auslöschung
- Shadowing: Signalabschwächung aufgrund von Blockaden oder Hindernissen
- Reflexion an großen Hindernissen: Signale werden von großen Objekten reflektiert und können dadurch mehrere Signalpfade erreichen.
- Brechung: Signaländerung beim Durchqueren von Materialien unterschiedlicher Dichte.
- Streuung an kleinen Hindernissen: Das Signal wird an kleinen Objekten gestreut und kann dadurch in verschiedene Richtungen abgelenkt werden
- Beugung an Kanten: Das Signal wird um Hindernisse herum gebeugt und kann dadurch in bestimmten Bereichen empfangen werden, wo die Sichtlinien blockiert sind.

Dadurch das das Signal viele Verschiedene Pfade zwischen Sender und Empfänger gehen kann, kann es zu Zeitlicher Dispersion kommen, dabei wird das Signal über die Zeit verteilt und es kommt zu Interferenzen mit "benachbarten" Symbolen, sogenannter Inter-Symbol-Interferenz(ISI). Dabei kann das Signal den Empfänger direkt und Phasenverschoben erreichen oder das Signal ist verzerrt bedingt durch die Phase der anderen Pfade.

Auch Bewegung kann einen Einfluss auf die Kanalcharakteristiken haben:
- Der Signalweg ändert sich
- Unterschiedliche Verzögerungs Variationen der verschiedenen Signal teile.
- Unterschiedliche Phasen der Signal teile.
- Kurzzeit-Fading:
	- Schnelle Änderungen in der empfangenen Änderungen durch Interferenz

Zusätzliche Änderungen können sich durch die Entfernung zum Sender, die Position von Hindernissen, Langzeit-Fading(Langsame Änderung der empfangenen Signalstärke) oder durch Doppler-Verschiebung ergeben. Beim Dopplereffekt verschiebt sich die Frequenz des Signals.

## Analoge vs Digitale Signale

Analoge Signale verlaufen über eine kontinuierliche Zeit und kontinuierliche Werte wobei Digitale Signale in Diskreter Zeit und Diskreten Werten Laufen.

![signal](Kommunkikationssysteme/attachments/signal.png)

---

Informationen können über die Medien übertragen werden, indem eine physikalische Eigenschaft wie Spannung oder Strom variiert wird.
- Amplitude
- Frequenz
- Phasenverschiebung

Als sogenannte Carrier-Wave benutzt man Typischer weise die Sinus-Kurve. Die Signal Kurve wird dann folgendermassen bestimmt:
$$c(t) = A \sin(2\pi f t + \phi)$$
wobei $f$ die Frequenz $f=\frac{1}{T}$ mit $T$ als Periode, $A$ als Amplitude und $\phi$ als Phasenverschiebung.

Durch die [[Fourier-Analyse]] können mehrere Wellen auf ein Medium en- und -decoded Werden.

## Nyquist's Theorem

In einem Ungestörten-Pefekten Kanal können Maximal
$$2H \log_{2} V \frac{bit}{s}$$
übertragen werden wobei $H$ die Bandbreite ist, falls das Signal aus $V$ diskreten Level besteht.

Da wir quasi nie einen Perfekten-Rausch freien Kanal haben benutzen wir Shannon's Theorem.

## Shannon's Theorem

$$H \log_{2}\left(1+ \frac{S}{N}\right) \frac{bit}{s}$$
Wobei $H$ wieder die Bandbreite bezeichnet und $\frac{S}{N}$ das Signal-Rausch Verhältnis ist.