<template>
    <div style="background-color: #253984; padding-top:2vh; padding-bottom:5vh; height:fit-content">
        <div class="flex flex-column font-normal items-start justify-start text-sm mobile-global-margins">
            <div class="flex w-full flex-row items-center pt-2 justify-between text-xs-responsive">
                <div class="w-1/6">
                    <nuxt-link to="/">  
                        <img style="width:27vw; height:auto; max-width:100vw;" :src="logo" />
                    </nuxt-link>
                </div>
                <div id="last-column" class="flex flex-row" >
                    <a href="https://www.facebook.com/edustream.vienna" style="margin-right:15%" target="_blank">
                        <img style="width: 12vw; height: auto;" :src="facebookLogo" />
                    </a>
                    <a href="https://www.instagram.com/edustream.at" target="_blank">
                        <img style="width: 12vw; height: auto;" :src="instagramLogo" />
                    </a>
                </div>
            </div>
            <div class="flex flex-row pt-10 pb-20 w-full justify-between items-start mobile-text-base-responsive">
                <div class="w-1/3">
                    <div class="flex flex-column items-start justify-around">
                        <h1 class="mobile-page-title-text pb-10 font-bold">{{$t('menu.courses.self')}}</h1>
                        <nuxt-link class="pt-7 hover:no-underline text-white" :to="localePath('/courses/german')">{{$t('menu.courses.de_short')}}</nuxt-link>
                        <nuxt-link class="pt-7 hover:no-underline text-white" :to="localePath('/courses/english')">{{$t('menu.courses.en_short')}}</nuxt-link>
                        <nuxt-link class="pt-7 hover:no-underline text-white" :to="localePath('/courses/italian')">{{$t('menu.courses.it_short')}}</nuxt-link>
                    </div>
                </div>
                <div class="w-1/3">
                    <div class="flex flex-column items-start justify-around">
                        <h1 class="mobile-page-title-text pb-10 font-bold">{{$t('menu.exams.self')}}</h1>
                        <nuxt-link class="pt-7 hover:no-underline text-white" :to="localePath('/exams/oif')">OIF</nuxt-link>
                        <nuxt-link class="pt-7 hover:no-underline text-white" :to="localePath('/exams/osd')">OSD</nuxt-link>
                    </div>
                </div>
                <div class="flex flex-column w-1/3 justify-around">
                    <h1 class="mobile-page-title-text pb-10 font-bold">{{$t('menu.about_us.self')}}</h1>
                    <nuxt-link class="pt-7 hover:no-underline text-white" :to="localePath('/about/info')">{{$t('menu.about_us.about_us')}}</nuxt-link>
                    <nuxt-link class="pt-7 hover:no-underline text-white" :to="localePath('/about/contacts')">{{$t('menu.about_us.contacts')}}</nuxt-link>
                </div>
            </div>
                <div class="flex w-full flex-column h-fit justify-start items-start mobile-text-base-responsive" style="height:35vh; border-top: 1px solid #6A8ACA; padding-top:3vh">
                    <h1 class="font-bold" style="font-size: calc(6px + 3.90625vw);">Address</h1>
                    <p class="my-7">Rennweg 9/6, 1030 Wien</p>
                    <p class="mobile-address-margin">{{$t('footer.opening_hours')}}</p>
                    <p class="mobile-address-margin">{{$t('footer.mon_thu')}}</p>
                    <p class="mobile-address-margin">{{$t('footer.friday')}}</p>
                    <p class="mobile-address-margin" style="margin-bottom:3vh">{{$t('footer.sat_sun')}}</p>
                    <div class="flex flex-row" style="margin-bottom:2vh">
                        <img style="width: 5vw; height: auto" :src="phoneIcon" />
                        <div class="text-white pl-1" v-html="$t('footer.phone_number')"></div>
                    </div>
                    <div class="flex flex-row" style="">
                        <img style="width: 5vw; height: auto" :src="emailIcon" />
                        <div class="text-white pl-1" v-html="$t('footer.email_address')"></div>
                    </div>
                </div>
            <div class="font-normal flex w-full w-full items-center justify-between  py-7 mobile-mwd-text-responsive" style="border-bottom: 1px solid #6A8ACA; border-top: 1px solid #6A8ACA;">
                <p class="w-full leading-normal">
                    {{$t('footer.m/w/d')}}
                </p>                
            </div>
            <div class="font-normal flex w-full flex-row items-center justify-center pb-1 pt-3 mobile-bottom-links-text-responsive" style="border-top-width: 1px;">
                
                <button type="button" class="" @click="$bvModal.show('modal-m-2')" >
                    <p class="mobile-bottom-links-text-responsive">AGB |</p>
                </button>
                <button type="button" class="" @click="$bvModal.show('modal-m-3')" >
                    <p class="mobile-bottom-links-text-responsive">Impressum |</p>
                </button>
                <button type="button" class="" @click="$bvModal.show('modal-m-4')" >
                    <p class="mobile-bottom-links-text-responsive">Datenschutz</p>
                </button>
            </div>
            <p class="font-normal text-white mx-auto mobile-bottom-links-text-responsive pt-5 cursor-default">?? 2022 EduStream GmbH</p>
        </div>
        <p class="hidden">Made by Artem Vorozhtsov, aivorozhtcov@gmail.com</p>
        <b-modal centered :busy="true" id="modal-m-2" :hide-header='true' :hide-footer='true' style="width:90%;">
        
        <div class="flex flex-column" style="margin-left:7%; margin-right:7%">
            <div class="t390__wrapper t-align_center"> 
                <div class="text-center pb-3" style="font-size: calc(9px + 5.61625vw);"><strong>Allgemeine Gesch??ftsb<br />edingungen EDUStream GmbH</strong></div> 
                <div class="text-center mobile-text-base-responsive" style=""><strong>1.Geltungsbereich</strong><br><br>Die Allgemeinen Gesch??ftsbedingungen (AGB) gelten f??r alle Gesch??fte, die sich auf Sprach, Fachkurse sowie Pr??fungen beziehen, die zwischen der Firma EDUStream GmbH (nachfolgend: EDUStream GmbH) und dessen Kunden abgeschlossen werden.<br>Die Fassung der Allgemeinen Gesch??ftsbedingungen, die zum Zeitpunkt des Vertragsschlusses g??ltig war, ist ma??gebend. Die Allgemeine Gesch??ftsbedingungen gelten auch f??r k??nftige Vereinbarungen, auch wenn in Erg??nzungsvertr??ge nicht ausdr??cklich darauf hingewiesen wird. Abweichungen von diesen Allgemeinen Gesch??ftsbedingungen sind m??glich, wenn dies in den entsprechenden Vertrag zwischen der EDUStream GmbH und dessen Kunden schriftlich vereinbart wurde.<br>Wenn die Kunden Minderj??hrige sind, dann m??ssen sie sich durch bevollm??chtigte gesetzliche oder vertragliche Vertreter vertreten lassen. Der Vertreter haftet der EDUStream GmbH f??r finanzielle Verpflichtungen, die aus dem Vertrag folgen, sowie f??r m??gliche Sch??den.<br>Alle relevanten Beschreibungen, die f??r Personen gelten, gelten f??r Frauen und f??r M??nner gleicherma??en.<br><br><br><strong>2.Kursteilnahmebedingungen&nbsp;</strong><br>Die Kurse sind f??r Kinder, Jugendliche und Erwachsene bestimmt. Falls es zus??tzliche Bedingungen f??r die Teilnahme an Kursen gibt, werden diese in der Kurs- oder Veranstaltungsbeschreibung separat angegeben und m??ssen vom Kunden beachten werden.<br><strong>&nbsp;</strong><br>Die Anmeldung zu den Kursen der EDUStream GmbH erfolgt pers??nlich, telefonisch oder schriftlich.<br>Die pers??nliche Anmeldung erfolgt im B??ro der Firma EDUStream GmbH unter der Adresse Rennweg 9, B??ro 6, 1030 Wien, w??hrend der ??ffnungszeiten der Sprachschule: Montag bis Donnerstag von 9.00 bis 17:00 Uhr, Freitag von 9.00 bis 15.00 Uhr. Die Kunden k??nnen sich auch unter der Telefonnummer + 43 1 890 89 48 oder schriftlich unter der E-Mail-Adresse:&nbsp;<a href="mailto:info@edu-stream.at">info@edu-stream.at</a>&nbsp;anmelden.<br>Um sich anzumelden, m??ssen Sie unserer Datenschutzerkl??rung zustimmen und unterschreiben sowie die Kursgeb??hr bezahlen. Die Bedingungen dieser AGB gelten als vom Kunden akzeptiert und best??tigt, sobald der Kunde die Zahlung auf die in den AGB angegebene Zahlungsart und zu den dort genannten Bedingungen get??tigt und die Anmeldung unterschrieben hat. Die Reihenfolge des Zahlungseingangs bestimmt die Reihenfolge der Anmeldung f??r den Kurs.<br>Die Bestimmung des angemessenen Niveaus des Kurses (dies bezieht sich zun??chst auf Sprachkurse) erfolgt auf der Grundlage eines Einstufungstests, der vor der Anmeldung zum Kurs durchgef??hrt wird.<br><strong>3</strong>.<strong>Kursgeb??hr&nbsp;</strong><br><br>Die Kosten des entsprechenden Kurses sind in der Beschreibung der Kurse auf der Website&nbsp;<a href="http://www.edu-stream.at/">www.edu-stream.at</a>&nbsp;angegeben, oder man kann sie vor Ort (EDUStream GmbH) anfragen.<br>Die Kosten des Kurses beinhalten nicht die Kosten der Lehrb??cher, der Ausfl??ge und der Besichtigungen.<br>Der Kurs wird mit der erforderlichen Mindestteilnehmerzahl durchgef??hrt. EDUStream GmbH beh??lt sich das Recht vor, im Falle eines Teilnehmermangels einen Kurs durchzuf??hren, wenn weniger Teilnehmer als n??tig anwesend sind, wobei die Anzahl der Kurseinheiten verringert oder die Kosten des Kurses erh??ht werden. Wenn Kunden damit nicht einverstanden sind, k??nnen sie den geplanten Kurs pausieren oder eine R??ckerstattung der gezahlten Kursgeb??hr zur??ckverlangen.<br><br><br><strong>4.Angebote</strong><br>Die Angaben ??ber die aktuellen Rabatte k??nnen Sie auf der Webseite&nbsp;<a href="http://www.edu-stream.at/">www.edu-stream.at</a>&nbsp;oder vor Ort (EDUStream GmbH, Rennweg 9/6 1030 Wien) nachfragen.<br><br><br><strong>5.Zahlungsbedingungen</strong><br><br>Die Zahlung des entsprechenden Kurses/ der Pr??fung erfolgt bar Vorort oder bargeldlos per Online??berweisung ohne Abz??ge und unter Angabe des entsprechenden Kurses in der Spalte ??Zweckverwendung?? sowie unter Angabe des Vor- und Nachnamens des Zahlers. Wenn der Kurs nicht vom Kursteilnehmer, sondern von einer anderen Person (Verwandten, anderen Personen) bezahlt wird, muss der Zahler im Feld ??Zweckverwendung?? den Vor- und Nachnamen des Kursteilnehmers angeben.<br><br>Die Zahlung f??r Kurse oder Pr??fungen erfolgt auf das unten angegebene Firmenkonto:<br><br>Kontoinhaber: EDUStream GmbH<br>IBAN: AT112011183826858900<br>BIC: GIBAATWWXXX<br>Bankname: Erste Bank der ??sterreichischen Sparkassen AG<br><br>Der entsprechende Betrag muss sp??testens 7 (sieben) Tage nach Rechnungsausstellung auf das Konto von EDUStream GmbH eingehen; Erfolgt die Anmeldung kurz vor Kursbeginn, muss die Zahlung in jedem Fall vor Kursbeginn eingegangen sein. Erfolgt die Anmeldung zu einem Zeitpunkt, an dem der Kurs bereits begonnen hat, ist die Rechnung innerhalb von 24 Stunden zu begleichen.<br><br>Bei Nichtzahlung ist eine Teilnahme an dem Kurs nicht m??glich.<br><br><br><strong>6.Allgemeine Informationen zu den Kursen, Rechten und Pflichten&nbsp;</strong><br><br>Die Dauer des Kurses ist in der Anzahl der Unterrichtseinheiten angegeben. Die Dauer einer Unterrichtseinheit (1 UE) betr??gt 45 Min.<br>Die Anzahl der Kursteilnehmer betr??gt 4 ??? 10 Personen.<br>EDUStream GmbH beh??lt sich das Recht vor:<br>- Den Lehrplan der angebotenen Kurse eigenst??ndig zu entwickeln;<br>- Den Kurs gem???? dem entwickelten Kursprogramm durchzuf??hren;<br>- Den geplanten Kursstart zu verschieben;<br>- Die Trainer im Laufe des Kurses bei Bedarf zu ersetzen;<br>- Die Teilnehmerzahl in den Kursen zu erweitern<br><br>EDUStream GmbH ist berechtigt und verpflichtet:<br>-Qualifiziertes Lehrpersonal mit einschl??giger Hochschulausbildung, hoher fachlicher Qualifikation und einschl??giger Berufserfahrung zu gewinnen;<br>-Den Lernprozess gem???? dem mit dem Kunden vereinbarten Lehrplan zu organisieren;<br><br><br><br><strong>7.Stornobedingungen</strong><br><strong>&nbsp;</strong><br><strong>Pr??fung</strong><br><br>Ein R??cktritt von der Pr??fung ist m??glich, es besteht jedoch kein Anspruch auf R??ckerstattung von bereits entrichteten Pr??fungsgeb??hren. Es wird Ihnen der n??chste Pr??fungstermin der jeweiligen Pr??fung angeboten.<br>Erfolgt der R??cktritt vor Pr??fungsbeginn, gilt die Pr??fung als nicht abgelegt. Wird die Pr??fung nach Beginn abgebrochen, gilt die Pr??fung als nicht bestanden.<br>Um im Falle eines R??cktritts von der Pr??fung oder eines Abbruchs der Pr??fung Krankheitsgr??nde geltend zu machen, muss beim zust??ndigen Pr??fungszentrum unverz??glich ein ??rztliches Attest vorgelegt werden. Liegt ein ??rztliches Attest vor, haben Sie die M??glichkeit den n??chsten Pr??fungstermin in Anspruch zu nehmen.<br>Sollte der Pr??fungstermin seitens des Pr??fungszentrums bzw. seitens des ??IF/??SD storniert werden, werden Sie automatisch f??r den n??chsten Pr??fungstermin angemeldet.<br><strong>Sprachkurs</strong><br>Der Kursteilnehmer (bei Minderj??hrigen vertreten durch den gesetzlichen Vertreter) meldet sich verbindlich zu dem bezeichneten Kurs an und verpflichtet sich zur Zahlung von Kursgeb??hren laut Rechnung. Die Kursteilnahme ist erst nach vollst??ndiger Bezahlung der jeweilig f??lligen Kursgeb??hr m??glich.<br><br>Die Kosten f??r Lehrb??cher werden nicht erstattet.<br><br><br><br><br><strong>8.Verbote</strong><br>In den R??umen des EDUStream GmbH besteht ein absolutes Rauchverbot.<br><br><br><br><strong>9.Schadensverg??tung</strong><br><br><br>Der Zubeh??r, der Raum und die Ausr??stung sollen unter sorgf??ltigem Umgang und Verwendung unterliegen. Die Kunden m??ssen alle von ihnen verursachten Sch??den erstatten.<br><br><br><br><strong>10.Verantwortungsausschlu??</strong><br><br><br>Die EDUStream GmbH haftet nicht, insbesondere auch bei Diebstahl, f??r pers??nliche Gegenst??nde des Kunden oder f??r die zur Verf??gung gestellten Schulungsunterlagen.<br>Der Lernprozess in den Kursen hat informativen Charakter. Der Lernerfolg des Kursteilnehmers und/oder ein positives Ergebnis bei den Pr??fungen k??nnen nicht gew??hrleistet werden.<br><br><br><strong>11.Anwendbares Recht und Gerichtsstand</strong><br>Als anwendbares Recht gilt ausschlie??lich nur ??sterreichisches Recht unter Ausschluss von Referenzstandards. Alle Streitigkeiten werden ausschlie??lich am zust??ndigen Gericht der Stadt Wien entschieden.<br>Aktualisiert, am 1.06.2022<br>EDUStream GmbH<br><br></div> 
            </div>
        </div>
      </b-modal>
      <b-modal centered :busy="true" id="modal-m-3" :hide-header='true' :hide-footer='true' style="width:90%;">
        
        <div class="flex flex-column" style="margin-left:7%; margin-right:7%">
            <div class="t390__wrapper t-align_center"> 
                <div class="text-center pb-3" style="font-size: calc(9px + 5.61625vw);">Impressum</div> 
                <div class="text-center mobile-text-base-responsive" style=""><strong>Herausgeberin dieser Webseite:</strong><br><br><strong>EDUStream Gmbh</strong><br>Sprachschule<br>FN 482870d, Handelsgericht Wien<br><br>Rennweg 9, Top 6<br>1030 Wien<br><br>Tel: +43 1 890-89-48<br>E-Mail:&nbsp;<a href="mailto:info@edu-stream.at">info@edu-stream.at</a><br><br><strong>Gesch??ftsf??hrung:</strong><br>Oborin Irina<br><br>UID: ATU 73006034<br><br><br></div> 
            </div>
        </div>
      </b-modal>
      <b-modal centered :busy="true" id="modal-m-4" :hide-header='true' :hide-footer='true' style="width:90%;">
        
        <div class="flex flex-column" style="margin-left:7%; margin-right:7%">
            <div class="t390__wrapper t-align_center mobile-text-base-responsive"> 
                ???????????? ???????????????????? - ???? ???????????????????? ?????????? ???????????? ???????? ??????????????
            </div>
        </div>
      </b-modal>
    </div>
    
</template>

<style scoped>
.mobile-page-title-text{
  font-size: calc(6px + 3.50625vw);
}
.text-xs-responsive{
  font-size: calc(1px + 0.70625vw);
}
.text-xs-header-responsive{
    font-size: calc(1px + 0.90625vw);
}
.text-2xs-responsive{
    font-size: calc(1px + 0.60625vw);
}

.mobile-mwd-text-responsive{
    font-size: calc(3px + 2.40625vw);
}
.mobile-bottom-links-text-responsive{
    font-size: calc(2.5px + 3.40625vw);
}
    
.mobile-address-margin{
    margin-top:1.5vh;
}
   

    p, h1{
        color:white;
    }

</style>

<script>

import logo from "~/assets/edu-stream_logo.png"
import facebookLogo from "~/assets/facebook_logo.svg"
import instagramLogo from "~/assets/instagram_logo.svg"
import phoneIcon from "~/assets/phone_icon.svg"
import emailIcon from "~/assets/email_icon.svg"


export default {
  data: function () {
    return {
      logo: logo,
      facebookLogo:facebookLogo,
      instagramLogo: instagramLogo,
      phoneIcon: phoneIcon,
      emailIcon: emailIcon
    }
  }
}



</script>