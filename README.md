# PUT netctl eduroam config
Konfiguracja sieci eduroam Politechiki Poznańskiej z użyciem netctl
<h2>Instrukcja</h2>
<ol>
  <li>Zaloguj się na <a href="https://elogin.put.poznan.pl">elogin PUT</a></li>
  <li>W zakładce certyfikaty wybierz "Twoje certyfikaty"</li>
  <li>Pobierz certyfikat, zapamiętaj hasło do pliku z certyfikatem, będzie później potrzebne</li>
  <li>Z zakładki "Certyfikaty CA" pobierz ADENA-CA</li>
  <li>Skopiuj plik konfiguracyjny put_eduroam do katalogu /etc/netctl/</li>
  <li>Umożliw odczyt pliku jedynie użytkownikowi root, żeby uchronić plik przed niepowołanym dostępem:<br/>
    <i>sudo chown root:root /etc/netctl/put_eduroam; sudo chmod 600 /etc/netctl/put_eduroam</i></li>
  <li>Edytuj plik swoim ulubionym edytorem, pamiętaj o uzyskaniu uprawnień root. (np. <i>sudo nano put_eduroam</i>)</li>
  <li>Uzupełnij pole <i>Interface</i> zastępując <i>twoj_interfejs</i> nazwą swojego interfejsu sieciowego. Listę dostępnych interfejsów możesz zobaczyć poleceniem: <i>ip link show</i>. W moim przypadku było to wlp2s0.</li>
  <li>Uzupełnij pole <i>identity</i> wpisując swój uczelniany adres email</li>
  <li>Uzupełnij pole <i>ca_cert</i> podając ścieżkę do pobranego pliku ADENA-CA</li>
  <li>Uzupełnij pole <i>private_key</i> podając ścieżkę do pobranego wcześniej twojego certyfikatu</li>
  <li>Uzupełnij pole <i>private_key_passwd</i> podając hasło do twojego certyfikatu. <b>UWAGA! NIE wpisuj tam hasła do elogin!</b></li>
  <li>Zapisz zmiany</li>
  <li>Uruchom profil wykonując komendę: <i>sudo netctl start put_eduroam</i>
  <li>Jeśli chcesz, żeby profil startował automatycznie wraz z uruchomieniem komputera wykonaj: <i>sudo netctl enable put_eduroam</i></li>
</ol>
