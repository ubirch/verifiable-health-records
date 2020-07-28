# Digitalisierung von Labor-Ergebnissen


# Datenschutzinfo Labore 


# Vorwort

Das System dient dazu, ein Testergebnis aus dem Labor datenschutzfreundlich in einem Blockchain-basierten Backend als Zertifikat abzulegen, so dass der User/die Userin das Testergebnis jederzeit gegen dieses Zertifikat verifizieren kann, um zu beweisen dass dieses Testergebnis valide ist. 

Die Daten werden im Labor über eine zur Verfügung gestellte Library anonymisiert und per DV an das System übergeben. Nur die getestete Person kann die Daten in der Folge mit ihrem eigenen Testergebnis in Zusammenhang bringen und zur Verifikation desselben verwenden.


## Zertifizierung

Labore können in Kooperation mit dem Partner D-TRUST/Bundesdruckerei einmalig einer Organisations-Verifikation unterzogen werden. Das Labor kann in der Folge mit einer qualifizierten elektronischen Signatur die Ergebnisse signieren. Diese Signatur fliesst als Element “C” in der System-Grafik im folgenden ein.


## Datenflüsse



1. Blockchain-Verankerung/Ausstellung von digitalen Zertifikaten

    Die Labor-Ergebnisse werden im Kontext des Labores (in den IT-Systemen) anonymisiert und auf Basis einer DVV (s.u.) an das Corona-Zertifikats-System übertragen. Dort werden die Daten anonym weiterverarbeitet, d.h. sie können ohne Einbezug des Getesteten nicht mehr auf eine Person zurückgerechnet werden.




<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image1.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image1.png "image_tooltip")



<table>
  <tr>
   <td>Schritt
   </td>
   <td>Beschreibung
   </td>
   <td>Ergebnis
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>Patientenstammdaten werden erhoben, Laborergebnis und Geheimnis 1 werden erzeugt.
   </td>
   <td>Personenbezogene Daten (A) liegen im Labor vor.
   </td>
  </tr>
  <tr>
   <td>2
   </td>
   <td>Hashwert 1 wird mit SHA256 gebildet.
   </td>
   <td>Hashwert enthält pseudonyme Daten (B) und liegt im Labor vor. 
   </td>
  </tr>
  <tr>
   <td>3
   </td>
   <td>Geheimnis 1 wird gelöscht
   </td>
   <td>B ist anonym
   </td>
  </tr>
  <tr>
   <td>4
   </td>
   <td>Signatur (C) wird erstellt
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>5
   </td>
   <td>Übermittlung an UBIRCH
   </td>
   <td>B+C werden in Datenbank gespeichert
   </td>
  </tr>
  <tr>
   <td>6
   </td>
   <td>Weiterverarbeitung mit Geheimnis 2 (D)
   </td>
   <td>Reserve für Opt-Out
   </td>
  </tr>
  <tr>
   <td>7
   </td>
   <td>Verankerung in der öffentlichen Blockchain
   </td>
   <td>F ist anonym
   </td>
  </tr>
</table>




2. Verifikation gegen die Zertifikats-Information in der Blockchain

    Für die Verifikation kann nun eine getestete Person Ihr Testergebnis in digitaler Form vorzeigen (z.B. als QR code). Die verifizierende Stelle kann aus dieser “Behauptung” einen Prüf-Hash berechnen und über das Corona-Zertifikats-System verifizieren, ob die Aussage des gezeigten Test-Ergebnisses stimmt und wirklich aus einem verifizierten Labor stammt.




<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image2.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image2.png "image_tooltip")



<table>
  <tr>
   <td>Schritt
   </td>
   <td>Beschreibung
   </td>
   <td>Ergebnis
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>Patientenstammdaten + Testergebnis + Geheimnis werden abgefragt (in QR Code kodiert).
   </td>
   <td>Personenbezogene Daten (A) liegen beim Verifizierer vor.
   </td>
  </tr>
  <tr>
   <td>2
   </td>
   <td>Hashwert 1 wird mit SHA256 gebildet.
   </td>
   <td>Hashwert enthält pseudonyme Daten (B) und liegt beim Verifzierer vor. 
   </td>
  </tr>
  <tr>
   <td>3
   </td>
   <td>Hashwert 1 wird an UBIRCH übermittelt
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>4
   </td>
   <td>Mit Hashwert 1 werden die Signatur (C) und Geheimnis 2 (D) ermittelt.
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>5
   </td>
   <td>Weiterverarbeitung inkl. Geheimnis 2 (D)
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>6
   </td>
   <td>Abfrage des anonymen Datums in Blockchain
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>7
   </td>
   <td>Übermittlung Prüfergebnis für (B)
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>8
   </td>
   <td>Hashwert 1 und Patientenstammdaten werden gelöscht
   </td>
   <td>B bis F sind anonym
   </td>
  </tr>
</table>



## Datenschutzrechtliche Grundlagen

Die einzelnen Schritte der Datenverarbeitung sind jeweils datenschutzrechtlich gerechtfertigt und stehen im Einklang mit der DSGVO. Dabei ist je nach Konstellation sowohl eine rechtfertigende Einwilligung des Probanden als auch eine Rechtfertigung mit berechtigten Interessen des Labors denkbar. In jedem Falle muss der Proband die Wahl haben, ob sein Testergebnis in anonymisierter Form gespeichert und für eine spätere Verifikation abgelegt wird. 



1. Rechtfertigung mit einer Einwilligung (Art. 6 Abs. 1 S. 1 lit. a DSGVO)

    In Betracht kommt eine Einwilligung des Probanden. Dafür muss der Proband vor der Speicherung des Testergebnisses erklären, dass er mit der dauerhaften Speicherung der Daten in der beschriebenen Form einverstanden ist. 


    Die Einwilligung muss transparent und freiwillig sein und den übrigen Anforderungen aus Art. 7 DSGVO genügen. 


    Das gesamte Prozedere muss dem Probanden in transparenter Form erläutert werden, damit sich die Einwilligung auf den gesamten Vorgang bezieht.

2. Rechtfertigung mit berechtigten Interessen (Art. 6 Abs. 1 S. 1 lit. f DSGVO)

    Auch ohne eine Einwilligung ist eine datenschutzrechtliche Rechtfertigung denkbar. Im Folgenden werden die einzelnen Schritte hinsichtlich ihrer datenschutzrechtlichen Zulässigkeit kurz skizziert:

1. Datenübermittlung vom Probanden (ggf. über den Arzt) an das Labor
2. Hashwertbildung aus den Daten (A)
3. Löschung des Geheimnisses und Anonymisierung der Daten
4. Signierung des verhashten Testergebnisses und die Übermittlung an UBIRCH 
5. Erneute Hashwertbildung und Speicherung in der Blockchain
6. Verifizierung 

    Im Einzelnen:

1. Die Datenübermittlung vom Probanden bzw. behandelnden Arzt an das Labor geschieht aufgrund der Erfüllung des Behandlungsvertrages (Art. 6 Abs. 1 S. 1 lit. b DSGVO) oder einer Einwilligung des Probanden (Art. 6 Abs. 1 S. 1 lit. a DSGVO).
2. Die Hashwertbildung aus den personenbezogenen Daten des Probanden, dem PCR und dem Geheimnis (A) ist zunächst eine Pseudonymisierung der Daten (Das Labor verhasht die Daten, ist jedoch zunächst im Besitz des Geheimnisses, und könnte mit den gleichen Daten wieder auf den gleichen Hashwert kommen, so dass es sich um pseudonyme Daten handelt). 
    *   Pseudonymisierung ist eine Datenverarbeitung, die rechtfertigungsbedürftig ist.
    *   Zwar handelt es sich jedenfalls bei den Testergebnissen um Gesundheitsdaten, so dass grundsätzlich die besonderen Voraussetzungen von Art. 9 Abs. 2 DSGVO gelten. Doch geht die herrschende Literatur davon aus, dass für Datenverarbeitungsvorgänge, die dem Betroffenen und dem Schutz seiner Daten dienen (wie Pseudonymisierung, Anonymisierung, Löschung), nicht die Voraussetzungen von Art. 9 DSGVO gelten, sondern dieser um diese Fälle teleologisch zu reduzieren ist (vgl. Hornung/ Wagner, ZD 2020, 223, 225 mit ausführlicher Begründung). Demnach können derartige Datenverarbeitungsvorgänge auch nach Art. 6 Abs. 1 S. 1 lit. f DSGVO gerechtfertigt sein.
    *   Die drei maßgeblichen Voraussetzungen liegen hier vor:
*   Die Verarbeitung entspricht einem berechtigten Interesse des Labors, namentlich dem Interesse an der pseudonymen/anonymen Speicherung des Testergebnisses zur späteren Verifikation für den Probanden, nicht zuletzt um dem Datenschutzgrundprinzip der Datenminimierung aus Art. 5 Abs. 1 lit. e) DSGVO zu entsprechen.
*   Die Verarbeitung ist für diesen Zweck auch erforderlich. 
*   Angesichts dessen, dass der Proband weiß, dass die Daten pseudonym und gesichert gespeichert werden, stehen seine Interessen auch nicht entgegen. Hinzu kommt, dass Vorkehrungen getroffen werden, dass die Daten für Dritte nicht einsehbar sind.
    *   Voraussetzung ist, dass der Proband über die Speicherung des verhashten Testergebnisses zum Zwecke der späteren Verifikation informiert wird und die Speicherung optional ist. 
3. Durch die Löschung des Geheimnis im Anschluss an die Hashwertbildung bei dem Labor werden die Daten für das Labor (und alle anderen Beteiligten) anonym. Ohne das Geheimnis kann niemand den gleichen Hashwert bilden und eine Zuordnung nicht vornehmen. 
    *   Auch die Anonymisierung ist nach überwiegender Ansicht eine Verarbeitung, die rechtfertigungsbedürftig ist (Art.-29-Datenschutzgruppe, WP 216, S. 8, 12; Hansen in Simitis/Hornung/Spiecker, Datenschutzrecht, 2019, Art. 4 Nr. 5, Rn. 23). 
    *   Bei der Rechtfertigung gelten die gleichen Erwägungen, wie bei der Pseudonymisierung: Art. 9 DSGVO ist möglicherweise ohnehin nicht anwendbar, weil es um die Anonymisierung eines Hashwerts (und nicht Gesundheitsdaten) geht, jedenfalls aber ist Art. 9 DSGVO um die Fälle der Anonymisierung teleologisch zu reduzieren (s.o.). 
    *   Für die Interessenabwägung gelten die Ausführung zu (b) entsprechend.
4. Die Signierung des verhashten Testergebnisses und die Übermittlung an UBIRCH ist streng genommen schon kein rechtfertigungsbedürftiger Vorgang, weil die verarbeiteten Daten (B+C) nach der Löschung des Geheimnisses bei dem Labor sowohl für das Labor, als auch UBIRCH anonym sind. Niemand außer dem Probanden selbst kann die einzelnen Datensätze einzelnen natürlichen Personen zuordnen. Die verhashten Daten liegen wie verschlüsselte Daten, deren Schlüssel allein der Inhaber der Daten hat, in der Datenbank. 

        Unterstellt man ungeachtet dessen, dass es sich insbesondere bei dem Hashwert (B) noch um pseudonyme Informationen handelt, ist die Übermittlung an UBIRCH und die dortige Speicherung rechtfertigungsbedürftig. 


        Diese Rechtfertigung ergibt sich ggf. erneut aus berechtigten Interessen (Art. 6 Abs. 1 S. 1 lit. f DSGVO). 

    *   Ein solches besteht im Interesse des Labors, die vom Patienten gewünschte Verifikationsmöglichkeit mit Unterstützung eines verlässlichen und fähigen Dienstleisters mit der entsprechenden technischen (Blockchain-)Infrastruktur anbieten zu können. Entsprechende erfolgt die Verarbeitung der Daten bei UBIRCH im Auftrag des Labors unter Abschluss einer entsprechenden Auftragsverarbeitungsvereinbarung nach Art. 28 DSGVO zwischen Labor und UBIRCH. 
    *   UBIRCH ist dann wegen Art. 4 Nr. 10 DSGVO nicht Dritter. 
    *   Für die Interessenabwägung im Übrigen gelten die Überlegungen zur Pseudonymisierung bei (b) entsprechend.
5. Die erneute Hashwertbildung bei UBIRCH (D) und die Speicherung der Hashwerte in den Merkle-Bäumen und der Blockchain (E+F) sind jeweils Verarbeitung anonymer Daten, weil jedenfalls für UBIRCH diese Daten anonym sind. UBIRCH hat keinerlei Möglichkeit, ohne Zutun des Probanden einen Bezug zu diesem herzustellen.  \
Sieht man ungeachtet dessen in der erneuten Hashwertbildung eine Anonymisierung zunächst pseudonymer Daten und verlangt man dafür nach der wohl h.M. eine gesetzliche Rechtfertigung, ist diese wiederum ohne Weiteres durch Art. 6 Abs. 1 S. 1 lit. f DSGVO gerechtfertigt. Das berechtigte Interesse des Verantwortlichen (Labor) besteht auch hier nicht zuletzt darin, den Vorgaben der DSGVO entsprechend auf eine umfassende Datenminimierung entsprechend Art. 5 Abs. 1 lit. e) DSGVO hinzuwirken. zudem wird UBIRCH in der AV-Vereinbarung mit dem Labor explizit angewiesen, diesen Hashwert für die spätere Verifikation des Tests und die Speicherung in der Blockchain zu bilden.
6. Auch bei der Verifizierung findet eine Datenverarbeitung statt. Angestoßen vom Probanden werden die bei UBIRCH vorhandenen Hashwerte mit dem vom Probanden selbst neu erzeugten Hashwert verglichen. Der Proband initiiert eine Übermittlung des Hashwerts an UBIRCH. 

        Für UBIRCH ist dabei nicht erkennbar, wessen Daten der jeweils angefragte Hashwert betrifft. Selbst wenn man entgegen der oben dargestellten Erwägungen annehmen wollte, dass die Hashwerte in diesem Zeitpunkt noch als personenbezogene Daten angesehen werden, ist die Datenverarbeitung jedoch gerechtfertigt, weil der Proband genau diesen Abgleich anstößt. 


        Rechtsgrundlage ist Art. 6 Abs. 1 S. 1 lit. b DSGVO, weil UBIRCH den Abgleich (möglicherweise sogar dem Probanden) schuldet. Alternativ kommt eine Rechtfertigung nach Art. 6 Abs. 1 S. 1 lit. f DSGVO in Betracht, weil die Datenverarbeitung im Interesse von UBIRCH liegt, für den Zweck erforderlich ist und der Betroffene jedenfalls mit dem Abgleich rechnet, weil er ihn selbst angestoßen hat. 



## Datenverarbeitungsvereinbarung (DVV)

Durch die Löschung des Geheimnisses bei dem Labor sind die Hashwerte für das Labor und UBIRCH anonyme Daten (s.o.). Für diese Verarbeitung wird eine Datenverarbeitungsvereinbarung zwischen UBIRCH und dem Labor geschlossen. 

Diese DV-Vereinbarung beinhaltet die Anweisung zur Anonymisierung der Daten vor der Weiterverarbeitung (E). 

Die AV-Vereinbarung gilt für die Verarbeitung der Hashwerte durch UBIRCH im Auftrag des Labors und entspricht den Vorgaben von Art. 28 DSGVO. 

UBIRCH bietet hier ein entsprechendes Template an. 


## Anonymisierung der Daten

Bevor UBIRCH Daten in die Blockchain speichert, werden zwei Anonymisierungsschritte vorgenommen: 



*   Zum einen wird nach der Hashwertbildung (A) das Geheimnis bei dem Labor gelöscht, so dass eine erneute Erstellung des gleichen Hashwerts nicht mehr möglich und eine Zuordnung der gespeicherten Daten (B) unmöglich ist. Eine Zuordnung der Daten ist dann nur noch durch den Probanden selbst möglich.

    Unter Berücksichtigung des Grundsatzes des relativen Personenbezugs stellt bereits diese Vorgehensweise eine Anonymisierung der Daten dar, weil sich aus Sicht des jeweils Verantwortlichen (Labor und UBIRCH) nach unwiderruflicher Löschung des Geheimnisses kein Bezug mehr zu einer natürlichen Person herstellen lässt. Durch eine Einweg-Verschlüsselung oder Verhashung entstehen gewöhnlich anonymisierte Daten, es sei denn, der jeweils anderen Stelle stehen Mittel zur Verfügung, um den Personenbezug mit verhältnismäßigem Aufwand wiederherzustellen (vgl. Arning/Rothkegel in Taeger/ Gabel, DSGVO, 3. Aufl. 2019, Art. 4 Rn. 51). Das Geheimnis als Schlüssel stellt vorliegend das einzige den Beteiligten potenziell zur Verfügung stehende Mittel zur Zuordnung der Daten zu einer natürlichen Person dar. Insofern wird der Schlüssel nicht (wie bei einer Pseudonymisierung) lediglich sicher (bei einer anderen verantwortlichen Stelle) aufbewahrt, sondern unwiderruflich aus der Sphäre und damit jeder Zugriffsmöglichkeit von Labor und UBIRCH gelöscht, sodass eine Re-Identifizierung nicht möglich ist.

*   Diese Daten (B)+(C) werden anschließend durch UBIRCH über SHA512 erneut verhasht (E). Die in die Blockchain geschriebenen Daten lassen sich nicht zurückverfolgen. Insbesondere werden weder dem Labor noch UBIRCH durch die Abfrage per QR-Code zusätzliche Informationen oder Mittel zur Verfügung gestellt, die eine Zuordnung der Testergebnisse zu einer bestimmten Person ermöglichen würden. Es kann lediglich ermittelt werden, ob die Kombination aus (B) und (C) zu einem früheren Zeitpunkt vom betreffenden signiert und in die Blockchain geschrieben wurde. 

Die Daten sind demnach anonym zu betrachten, weil ohne die Mitwirkung des Probanden keine Möglichkeit besteht, diese Daten einer Person zuzuordnen.


## Geheimhaltungsverpflichtung 

UBIRCH unterwirft sich vertraglich einer Geheimhaltungsverpflichtung gem  § 203 Abs. 4 S. 2 Nr. 1 StGB.


## Datenschutz-Beauftragter

UBIRCH: 				Gregor Klar: klar@brainosphere.de


## Wahrung von Betroffenenrechten

Soweit personenbezogene Daten gespeichert werden, stehen den Probanden ihre Betroffenenrechte aus Art. 15 ff. DSGVO zu. Diese sind in der hier beschriebenen Konstellation an das Labor zu adressieren, weil diese Verantwortlicher ist.  



1. **Auskunft**

    Die vom Labor zu erteilende Auskunft kann sich nach Löschung des Geheimnis auf die unmittelbar bei dem Labor gespeicherten Daten beschränken. Zusätzlich kann noch eine Auskunft erfolgen, dass die Daten anonymisiert an UBIRCH übermittelt wurden. 


    UBIRCH ist zu einer Auskunft nicht in der Lage, weil UBIRCH eine Zuordnung zu einzelnen Personen nicht vornehmen kann. Auskunftsfähig ist UBIRCH nur, wenn der Proband mit seinem Geheimnis den Hashwert erneut erzeugt. Die Auskunft von UBIRCH würde sich dann allerdings darauf beschränken, dass ein entsprechender Datensatz gespeichert wurde. 

2. **Löschung**

    Da es sich bei den Daten im System um anonymisierte Daten handelt, kann eine Löschung nur durch den Betroffenen selbst unter Nutzung seines Geheimnisses veranlasst werden. Dies ist möglich und wird auch entsprechend protokolliert.
