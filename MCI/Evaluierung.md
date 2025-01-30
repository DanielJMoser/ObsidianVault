
import React, { useMemo } from 'react';

import {

IonCard,

IonCardContent,

IonGrid,

IonRow,

IonCol,

IonSelect,

IonSelectOption,

IonSegment,

IonSegmentButton,

IonIcon,

IonLabel,

} from '@ionic/react';

import {

barChartOutline,

analyticsOutline,

pieChartOutline,

timeOutline,

pulseOutline,

} from 'ionicons/icons';

import { EvaluationContext } from '../../../types/EvalTypes';

import {Options} from "./Options";

type MyChartType = 'bar' | 'line' | 'pie' | 'doughnut' | 'radar' | 'polarArea';

interface FiltersSectionProps {

evaluationData: EvaluationContext[];

selectedEvaluationId: number | null;

setSelectedEvaluationId: (id: number) => void;

selectedSemester: string;

setSelectedSemester: (semester: string) => void;

selectedChart: MyChartType;

setSelectedChart: (chartType: MyChartType) => void;

showTrend: boolean;

setShowTrend: (show: boolean) => void;

invertYAxis: boolean;

setInvertYAxis: (invert: boolean) => void;

}

interface GroupedCourse {

name: string;

semesters: {

id: number;

semester: string;

}[];

}

const FiltersSection: React.FC<FiltersSectionProps> = ({

evaluationData,

selectedEvaluationId,

setSelectedEvaluationId,

selectedSemester,

setSelectedSemester,

selectedChart,

setSelectedChart,

showTrend,

setShowTrend,

invertYAxis,

setInvertYAxis,

}) => {

// Group courses by name and collect their semester data

const groupedCourses = useMemo(() => {

const courseMap = new Map<string, GroupedCourse>();

evaluationData.forEach(evaluation => {

const existingCourse = courseMap.get(evaluation.name);

if (existingCourse) {

existingCourse.semesters.push({

id: evaluation.id,

semester: evaluation.semester

});

} else {

courseMap.set(evaluation.name, {

name: evaluation.name,

semesters: [{

id: evaluation.id,

semester: evaluation.semester

}]

});

}

});

return Array.from(courseMap.values());

}, [evaluationData]);

// Get available semesters for selected course

const availableSemesters = useMemo(() => {

const selectedCourse = groupedCourses.find(course =>

course.semesters.some(sem => sem.id === selectedEvaluationId)

);

return selectedCourse?.semesters.sort((a, b) =>

b.semester.localeCompare(a.semester)

) || [];

}, [selectedEvaluationId, groupedCourses]);

// Handle course selection change

const handleCourseChange = (courseName: string) => {

const course = groupedCourses.find(c => c.name === courseName);

if (course) {

// Select the most recent semester by default

const mostRecentSemester = course.semesters.sort((a, b) =>

b.semester.localeCompare(a.semester)

)[0];

setSelectedEvaluationId(mostRecentSemester.id);

setSelectedSemester(mostRecentSemester.semester);

}

};

// Handle semester selection change

const handleSemesterChange = (semester: string) => {

const selectedCourse = groupedCourses.find(course =>

course.semesters.some(sem => sem.id === selectedEvaluationId)

);

if (selectedCourse) {

const semesterData = selectedCourse.semesters.find(sem =>

sem.semester === semester

);

if (semesterData) {

setSelectedEvaluationId(semesterData.id);

setSelectedSemester(semester);

}

}

};

return (

<section className="filters-container">

<IonCard className="filter-card">

<IonCardContent>

<IonGrid>

<IonRow>

<IonCol size="12" sizeMd="6">

<IonSelect

value={groupedCourses.find(course =>

course.semesters.some(sem =>

sem.id === selectedEvaluationId

)

)?.name}

onIonChange={e => handleCourseChange(e.detail.value)}

label="Course"

labelPlacement="floating"

className="modern-select"

>

{groupedCourses.map((course) => (

<IonSelectOption key={course.name} value={course.name}>

{course.name}

</IonSelectOption>

))}

</IonSelect>

</IonCol>

<IonCol size="12" sizeMd="6">

<IonSelect

value={selectedSemester}

onIonChange={e => handleSemesterChange(e.detail.value)}

label="Semester"

labelPlacement="floating"

className="modern-select"

disabled={availableSemesters.length === 0}

>

{availableSemesters.map((sem) => (

<IonSelectOption key={sem.semester} value={sem.semester}>

{sem.semester}

</IonSelectOption>

))}

</IonSelect>

</IonCol>

</IonRow>

<IonRow>

<IonCol>

<IonSegment

value={selectedChart}

onIonChange={e => setSelectedChart(e.detail.value as MyChartType)}

className="chart-selector"

>

<IonSegmentButton value="bar">

<IonIcon icon={barChartOutline} />

<IonLabel>Bar</IonLabel>

</IonSegmentButton>

<IonSegmentButton value="line">

<IonIcon icon={analyticsOutline} />

<IonLabel>Line</IonLabel>

</IonSegmentButton>

<IonSegmentButton value="radar">

<IonIcon icon={pulseOutline} />

<IonLabel>Radar</IonLabel>

</IonSegmentButton>

<IonSegmentButton value="polarArea">

<IonIcon icon={pieChartOutline} />

<IonLabel>Polar</IonLabel>

</IonSegmentButton>

<IonSegmentButton value="pie">

<IonIcon icon={pieChartOutline} />

<IonLabel>Pie</IonLabel>

</IonSegmentButton>

<IonSegmentButton value="doughnut">

<IonIcon icon={timeOutline} />

<IonLabel>Ring</IonLabel>

</IonSegmentButton>

</IonSegment>

</IonCol>

</IonRow>

<IonRow className="mt-4">

<Options

showTrend={showTrend}

invertYAxis={invertYAxis}

onShowTrendChange={setShowTrend}

onInvertYAxisChange={setInvertYAxis}

/>

</IonRow>

</IonGrid>

</IonCardContent>

</IonCard>

</section>

);

};

export default FiltersSection;

// Filters Section

.filters-container {

.filter-card {

margin: 0;

box-shadow: 0 2px 4px rgba($text-color-rgb, 0.05);

border-radius: 12px;

background: $color-step-50;

border: 1px solid $border-color;

.modern-select {

--padding-start: 0;

--padding-end: 0;

--placeholder-color: $color-medium;

--placeholder-opacity: 0.8;

max-width: 100%;

width: 100%;

margin-bottom: 1rem;

&::part(label) {

color: $text-color;

font-size: 0.875rem;

}

}

.chart-selector {

--background: $background-color;

border-radius: 12px;

padding: 4px;

ion-segment-button {

--background-checked: $color-primary;

--color-checked: $color-primary-contrast;

--indicator-color: transparent;

min-height: 48px;

font-size: 0.875rem;

&::part(indicator) {

display: none;

}

ion-icon {

font-size: 1.25rem;

margin-bottom: 4px;

}

ion-label {

margin-top: 4px;

}

}

}

}

}

# Fragen (JSON)
Diese Fragen wurden so verbatim aus dem alten System übertragen:

```json
{
	"eval.lv_1.title.1": "1. Gesamtbeurteilung",  
"eval.lv_1.subtitle.1": "Wie beurteilen Sie die Lehrveranstaltung insgesamt?",  
"eval.lv_1.title.2": "2. Fachkompetenz des Lektors / der Lektorin",  
"eval.lv_1.subtitle.2": "Wie beurteilen Sie die Fachkompetenz des Lektors / der Lektorin?",  
"eval.lv_1.title.3": "3. Verständlichkeit der Inhalte",  
"eval.lv_1.subtitle.3": "Wie beurteilen Sie die Fähigkeit des Lektors / der Lektorin die Inhalte verständlich zu vermitteln?",  
"eval.lv_1.title.4": "4. Bereitschaft zur Beantwortung von Fragen",  
"eval.lv_1.subtitle.4": "Wie beurteilen Sie die Bereitschaft des Lektors / der Lektorin, Fragen von Studierenden zu beantworten?",  
"eval.lv_1.title.5": "5. Qualität der Unterlagen",  
"eval.lv_1.subtitle.5": "Wie beurteilen Sie die Qualität der zur Verfügung gestellten Unterlagen?",  
"eval.lv_1.title.6": "6. Methoden",  
"eval.lv_1.subtitle.6": "Wie beurteilen Sie den Einsatz der Methoden (Präsentation, Gruppenarbeit, Rollenspiel, Diskussion etc.)?",  
"eval.lv_1.title.7": "7. Praxisrelevanz",  
"eval.lv_1.subtitle.7": "Wie beurteilen Sie die Erläuterungen des Lehrstoffs anhand von Praxisbeispielen?",  
"eval.lv_1.title.8": "8. Zusammenarbeit mit dem Lektor / der Lektorin",  
"eval.lv_1.subtitle.8": "Wie gut hat Ihre Gruppe mit dem Lektor / der Lektorin zusammen gearbeitet?",  
"eval.lv_1.title.9": "9. Zusammenarbeit mit anderen Studierenden",  
"eval.lv_1.subtitle.9": "Wie gut war die Zusammenarbeit innerhalb der Studierenden?",  
"eval.lv_1.title.10": "10. Qualitative Fragen zur Lehrveranstaltung I",  
"eval.lv_1.subtitle.10": "Was hat Ihnen im Rahmen der Lehrveranstaltung besonders gut gefallen?",  
"eval.lv_1.title.11": "11. Qualitative Fragen zur Lehrveranstaltung II",  
"eval.lv_1.subtitle.11": "Was hat Ihnen im Rahmen der Lehrveranstaltung nicht gefallen?",  
"eval.lv_1.title.12": "12. Qualitative Fragen zur Lehrveranstaltung III",  
"eval.lv_1.subtitle.12": "Was würden Sie zur Lehrveranstaltung anregen?",  
  
"eval.lv_2.title.1": "1. Gesamtbeurteilung",  
"eval.lv_2.subtitle.1": "Wie beurteilen Sie die Lehrveranstaltung insgesamt?",  
"eval.lv_2.title.2": "2. Ziele",  
"eval.lv_2.subtitle.2": "Wie klar wurden die Ziele der LV durch den Lektor / die Lektorin vermittelt?",  
"eval.lv_2.title.3": "3. Fachkompetenz des Lektors / der Lektorin",  
"eval.lv_2.subtitle.3": "Wie beurteilen Sie die Fachkompetenz des Lektors / der Lektorin?",  
"eval.lv_2.title.4": "4. Verständlichkeit der Inhalte",  
"eval.lv_2.subtitle.4": "Wie beurteilen Sie die Fähigkeit des Lektors / der Lektorin die Inhalte verständlich zu vermitteln?",  
"eval.lv_2.title.5": "5. Bereitschaft zur Beantwortung von Fragen",  
"eval.lv_2.subtitle.5": "Wie beurteilen Sie die Bereitschaft des Lektors / der Lektorin, Fragen von Studierenden zu beantworten?",  
"eval.lv_2.title.6": "6. Qualität der Unterlagen",  
"eval.lv_2.subtitle.6": "Wie beurteilen Sie die Qualität der zur Verfügung gestellten Unterlagen?",  
"eval.lv_2.title.7": "7. Methoden",  
"eval.lv_2.subtitle.7": "Wie beurteilen Sie den Einsatz der Methoden (Präsentation, Gruppenarbeit, Rollenspiel, Diskussion etc.)?",  
"eval.lv_2.title.8": "8. Praxisrelevanz",  
"eval.lv_2.subtitle.8": "Wie beurteilen Sie die Erläuterungen des Lehrstoffs anhand von Praxisbeispielen?",  
"eval.lv_2.title.9": "9. Zusammenarbeit mit dem Lektor / der Lektorin",  
"eval.lv_2.subtitle.9": "Wie gut hat Ihre Gruppe mit dem Lektor / der Lektorin zusammen gearbeitet?",  
"eval.lv_2.title.10": "10. Veranstaltungsorganisation I",  
"eval.lv_2.subtitle.10": "Wie beurteilen Sie die Organisation und Betreuung durch das MCI?",  
"eval.lv_2.title.11": "11. Veranstaltungsorganisation II",  
"eval.lv_2.subtitle.11": "Wie beurteilen Sie die Seminarräume und Ausstattung?",  
"eval.lv_2.title.12": "12. Qualitative Fragen zur Lehrveranstaltung I",  
"eval.lv_2.subtitle.12": "Was hat Ihnen im Rahmen der Lehrveranstaltung besonders gut gefallen?",  
"eval.lv_2.title.13": "13. Qualitative Fragen zur Lehrveranstaltung II",  
"eval.lv_2.subtitle.13": "Was hat Ihnen im Rahmen der Lehrveranstaltung nicht gefallen?",  
"eval.lv_2.title.14": "14. Qualitative Fragen zur Lehrveranstaltung III",  
"eval.lv_2.subtitle.14": "Was würden Sie zur Lehrveranstaltung anregen?",  
"eval.lv_2.title.15": "14. Qualitative Fragen zur Lehrveranstaltung IV",  
"eval.lv_2.subtitle.15": "Zu welchen weiteren Themen sollte das MCI Veranstaltungen anbieten?",  
  
"eval.lv_3.title.1": "1. Gesamtbeurteilung",  
"eval.lv_3.subtitle.1": "Meine Gesamtbeurteilung der Lehrveranstaltung lautet wie folgt.",  
"eval.lv_3.title.2": "2. Beurteilung der Lehrveranstaltung im Detail",  
"eval.lv_3.subtitle.2": "Die LV-leitung macht einen fachlich kompetenten Eindruck",  
"eval.lv_3.title.3": "",  
"eval.lv_3.subtitle.3": "Die LV-Leitung verknüpft Theorie mit beruflicher Praxis mittels aktueller Beispiele.",  
"eval.lv_3.title.4": "",  
"eval.lv_3.subtitle.4": "Die LV-Leitung kommuniziert zu Beginn klare Lernziele und orientiert sich daran.",  
"eval.lv_3.title.5": "",  
"eval.lv_3.subtitle.5": "Die LV-Leitung gibt vorab klare Informationen zu Prüfungsmodalitäten und Benotung.",  
"eval.lv_3.title.6": "",  
"eval.lv_3.subtitle.6": "Die LV-Leitung verfolgt inhaltlich einen nachvollziehbar roten Faden.",  
"eval.lv_3.title.7": "",  
"eval.lv_3.subtitle.7": "Der Einsatz der didaktischen Methoden ist angemessen.",  
"eval.lv_3.title.8": "",  
"eval.lv_3.subtitle.8": "Die LV-Leitung begegnet den Studierenden respektvoll.",  
"eval.lv_3.title.9": "",  
"eval.lv_3.subtitle.9": "Die LV-Leitung fördert selbständiges Denken und Arbeiten.",  
"eval.lv_3.title.10": "",  
"eval.lv_3.subtitle.10": "Ich bereite Inhalte der Lehrveranstaltung eigenständig vor/nach.",  
"eval.lv_3.title.11": "",  
"eval.lv_3.subtitle.11": "Ich kann meine Fragen und Anliegen im Rahmen der Lehrveranstaltung aktiv einbringen.",  
"eval.lv_3.title.12": "3. Rahmenbedingungen",  
"eval.lv_3.subtitle.12": "Die Prüfungsleistung zu dieser Lehrveranstaltung wurde bereits zur Gänze erbracht.",  
"eval.lv_3.title.13": "",  
"eval.lv_3.subtitle.13": "Meine Leistungsbeurteilung zu dieser Lehrveranstaltung ist mir bereits bekannt.",  
"eval.lv_3.title.14": "",  
"eval.lv_3.subtitle.14": "Der Zeitpunkt der Lehrveranstaltung im Studienplan ist richtig gewählt.",  
"eval.lv_3.title.15": "4. Qualitative Fragen zur Lehrveranstaltung",  
"eval.lv_3.subtitle.15": "Was hat Ihnen an der Lehrveranstaltung besonders gut gefallen?",  
"eval.lv_3.title.16": "",  
"eval.lv_3.subtitle.16": "Was hat Ihnen an der Lehrveranstaltung nicht gefallen?",  
"eval.lv_3.title.17": "",  
"eval.lv_3.subtitle.17": "Was würden Sie zur Lehrveranstaltung anregen?"
}
```


## Aufbau
Wie zu erkennen, existieren aktuell drei Versionen des Fragebogens. Aus den gelieferten Daten lassen sich einige Schlüsse ziehen und fundierte Vermutungen anstellen. Dies sind aber nur Deduktionen, würde dazu beim morgigen Meeting Jochen nochmals befragen:

-  *lv_1* dürfte **bis 2015** verwendet worden sein.
- *lv_2* gilt vermutlich den **Executive-Lehrgängen**.
- *lv_3* wird wohl **ab 2016** verwendet.

Über die Schnittstelle müssten sowohl die Fragen (title und subtitle) als auch die Version mitgeliefert werden. 
## Vorschläge:
Damit die graphische Darstellung nicht überladen wirkt, bieten sich kürzere Versionen der Untertitel an. Diese reichen aus, um sich einen ersten, groben Überblick zu verschaffen. Ich schlage folgende Vormulierungen vor, da sie (trotz ihrer Knappheit) dennoch intuitiv eine Idee der darunterliegenden Information vermitteln. Einige "Kurztitel" sind zugegebener Maßen nicht ganz ideal (etwa: `"eval.lv_3.subtitle.14_short": "Zeitpunkt"`) sind nicht ganz ideal, aber vermutlich ausreichend.

```json
{
	"eval.lv_1.subtitle.1_short": "Gesamtbeurteilung",
  "eval.lv_1.subtitle.2_short": "Fachkompetenz",
  "eval.lv_1.subtitle.3_short": "Verständlichkeit",
  "eval.lv_1.subtitle.4_short": "Fragenbereitschaft",
  "eval.lv_1.subtitle.5_short": "Unterlagen",
  "eval.lv_1.subtitle.6_short": "Methoden",
  "eval.lv_1.subtitle.7_short": "Praxisbezug",
  "eval.lv_1.subtitle.8_short": "Zusammenarbeit Lektor",
  "eval.lv_1.subtitle.9_short": "Zusammenarbeit Studierende",
  "eval.lv_1.subtitle.10_short": "Positives Feedback",
  "eval.lv_1.subtitle.11_short": "Negatives Feedback",
  "eval.lv_1.subtitle.12_short": "Anregungen",
  
  "eval.lv_2.subtitle.1_short": "Gesamtbeurteilung",
  "eval.lv_2.subtitle.2_short": "Ziele",
  "eval.lv_2.subtitle.3_short": "Fachkompetenz",
  "eval.lv_2.subtitle.4_short": "Verständlichkeit",
  "eval.lv_2.subtitle.5_short": "Fragenbereitschaft",
  "eval.lv_2.subtitle.6_short": "Unterlagen",
  "eval.lv_2.subtitle.7_short": "Methoden",
  "eval.lv_2.subtitle.8_short": "Praxisbezug",
  "eval.lv_2.subtitle.9_short": "Zusammenarbeit Lektor",
  "eval.lv_2.subtitle.10_short": "Organisation MCI",
  "eval.lv_2.subtitle.11_short": "Seminarräume",
  "eval.lv_2.subtitle.12_short": "Positives Feedback",
  "eval.lv_2.subtitle.13_short": "Negatives Feedback",
  "eval.lv_2.subtitle.14_short": "Anregungen",
  "eval.lv_2.subtitle.15_short": "Weitere Themen",
  
  "eval.lv_3.subtitle.1_short": "Gesamtbeurteilung",
  "eval.lv_3.subtitle.2_short": "Fachkompetenz",
  "eval.lv_3.subtitle.3_short": "Praxisbezug",
  "eval.lv_3.subtitle.4_short": "Ziele",
  "eval.lv_3.subtitle.5_short": "Prüfungsinfos",
  "eval.lv_3.subtitle.6_short": "Roter Faden",
  "eval.lv_3.subtitle.7_short": "Methoden",
  "eval.lv_3.subtitle.8_short": "Respekt",
  "eval.lv_3.subtitle.9_short": "Selbständigkeit",
  "eval.lv_3.subtitle.10_short": "Vor-/Nachbereitung",
  "eval.lv_3.subtitle.11_short": "Fragen einbringen",
  "eval.lv_3.subtitle.12_short": "Prüfungsleistung",
  "eval.lv_3.subtitle.13_short": "Bekannte Bewertung",
  "eval.lv_3.subtitle.14_short": "Zeitpunkt",
  "eval.lv_3.subtitle.15_short": "Positives Feedback",
  "eval.lv_3.subtitle.16_short": "Negatives Feedback",
  "eval.lv_3.subtitle.17_short": "Anregungen"
}  
```


