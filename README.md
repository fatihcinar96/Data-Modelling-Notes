<h1>ADO.NET Nedir? </h1>
<h2>Active Data Object</h2>
<p>
    Veritabanı ile dili konuşturmak için kullanılır.Temel amacı,kendi yazdığınız arayüz yardımıyla SQL üzerinde istediğimiz sorguları çalıştıracak projeler oluşturmaktır.
</p>
<h2>ADO.NET Mimarisi</h2>
<p>
    Kendi içerisinde iki temel mimari barındırır.<br/>
    1-) Connected
    2-) Disconnected
</p>

<h2>Connected Mimari</h2>
<p>
Bu bağlantı şeklinde,uygulamamız tamamen bağlantı halindedir ve anlık olarak database de CRUD operasyonları yapılmaktadır.<br/>
Bağlantı sürekli açık olduğu için,veri okuma sistemi son satıra kadar açık kalır.Bu da biraz performanssızlığa sebep olur.
</p>
<h3><u>Sınıflar</u></h3>
<u>Command</u>
<p>
    Sorgularımızı ya da prosedürlerimizi çalıştırmamıza yarayan sınıftır.(SqlCommand,OracleCommand)
</p>
<h2>Disconnected Mimari</h2>
<p>
Bu bağlantı şeklinde uygulama veritabanını kullanmak için sürekli ona müracaat etmek yerine,veritabanının bir kopyasını RAM üzerine alır ve işlemleri RAM üzerinde yapar.<br/>
En büyükm avantajı performanstır.<br/>
Dezavantajı ise veriler her zaman güncel olmayabilir ve değişiklikleri veri tabanına aktarmak için ayrı bir işlem gerektirir.
</p>
<u>Command</u>
<p>Data Adapter:<br/> Veriyi çeker fakat görüntülemek için DataTable veya DataAdapter kullanılır.

<h1>Data Access Object Nedir?</h1>
<p>
Data Access Object in temel amacı sistemimizde kullandığımız nesnelerin çeşitli veri katmanlarına erişimini sistemden soyutlamaktır.

Klasik veritabanı kullanan çoğu uygulamada CRUD işlemleri bulunur.Günümüzde veri erişim teknolojileri(ADO,Entity vs) sürekli değişiyor.Eğer biz uygulamamızın bu değişikliklerden etkilenmesini istemiyorsak DAO Pattern kullanırız.<br/>
Bu sayede uygulamamız hem veri erişim katmanından(Data Access Layer) soyutlanıyor hem de veri erişim teknolojisinden bağımsız hale geliyor.
</p>

<h1>Data Access Layer Nedir?</h1>
<p>
Uygulamayla ilgili verilere erişmek ve üzerinde işlem yapmak için kullanılan katmandır.<br/>
Data Access Layer kullanılan uygulamalar sunucuya bağımlı ya da bağımzsız olabilir.
<br/>
Eğer Data Access Layer birden çok database tipini destekliyorsa uygulama DAL'ın konuşabildiği her veritabanını kullanabilir hale gelecektir.<br/>
Uygulamada böyle bir katman baştan planlanırsa,ileride sadece bu katman üzerinde değişiklik yaparak verilerin saklandığı yer değiştirilebilir.<br/>
Örneğin veriler bir MySQL veritabanından okunuyordur.Bu daha sonra SQL Server'a çevrilebilir veya provider bir XML web servisi de olabilir.Böyle bir durumda sadece Data Acess Layer katmanında değişiklik yaparsınız.Gerisi normal bir şekilde çalışmaya devam eder.
</p>
<h1>DBAL Nedir?</h1>
<p>
Database Abstraction Layer,veritabanı ile program arasında bağlantıyı sağlayan bir programlama arayüzüdür.<br/>Örnek olarak ben farklı türlerde veritabanı kullanabilirim.(Oracle,SQL vs.).Bu veritabanlarında sorgular farklı olabilir ve bu da projede karmaşıklığa sebep olabilir.<br/>DBAL'da ise ben sorguyu DBAL'a gönderirim.O ise komutu veritabanına gönderir ve dönen sonucu çekerek bize döner.Böylece program ve veritabanı arasında bir soyutlama sağlanmış olur.
</p>
<h1>DBMS Nedir?</h1>
<p>
    Database Management System,veritabanlarını oluşturma,yönetme yazılımıdır.DBMS programcıya sistematik bir yolla veriyi oluşturma,geri alma,güncelleme kısaca yönetmeyi sağlar.
    <br/>
    DBMS iki temel şeyi yönetir;
    <br/>
    -Veri<br/>
    -Mantıksal yapıyı tanımlayan şema<br/>
    <h3><u>Popüler veritabanı modelleri ve yönetim sistemleri</h3></u>
    -Relational DBMS<br/>
    -NoSQL DBMS<br/>
    -In Memory DBMS<br/>
    -Columnar DBMS<br/>
    -Cloud-based DBMS<br/>
    <h3><u>Popüler DBMS'ler</u></h3>
    -IBM DB2<br/>
    -MySQL<br/>
    -Oracle<br/>
    -MsSQL<br/>
    -PostgreSQL<br/>
</p>

<h1>JDBC Nedir?</h1>
<p>
    Java Database Connectivity,Java ile ilişkisel bir veritabanına erişmek ve verisel işlemler yapmak için program-veritabanı arasındaki bir köprüdür.Programdan bağımsız şekilde yazılabilir.
    <br/>
    JDBC Driver Manager sayesinde farklı veritabanlarına bağlanılabilir.<br/>
    <u>Statement</u><br/>
    Yazılan sorguları veri tabanına taşır.<br/>
    <u>Result Set</u><br/>
    Query sonucunu döner.<br/>
    <br/>
    <u>Aşağıdaki adımlar izlenerek gerçekleştirilir;</u><br/>
    -Connection açılır.<br/>
    -SQL sorgularını yazacağımız statement objesi oluşturulur.<br/>
    -Yazılan Query çalıştırılır.<br/>
    -Resultset ile veriler alınır.<br/>
    -Connection kapatılır.
</p>

<h1>ORM Nedir?</h1>
<p>
Object Relational Mapping,veritabanındaki tablomuza bağlayan ve veri alışverişini yapan metotdur.ORM tekniği belli bir programlama diline bağlı değildir ve her dilde kullanılabilir.<br/>
Bir çok ORM kütüphaneleri vardır.Bunlar ORM tools olarak adlandırılır.<br/>
Veritabanı işlemlerinin karmaşıklığını bizim için gizler ve veritabanından bağımsız olarak nesne modelimiz ile çalışmamızı sağlar.
<h2><u>ORM Avantajları</u></h2>
-Nesneye yönelik programlama metodu sunar.<br/>
-Yazılan kodun veritabanı çeşidiyle bağımlılığı olmaz.<br/>
-Test edilebilir kod yazmayı sağlar.<br/>
<h2><u>ORM Dezavantajları</u></h2>
-Performans sorunları.<br/>
-Kullanılan ORM aracını öğrenmek için harcanan zaman.
<h3><u>Bazı Popüler ORM Araçları</u></h3>
-Hibernate<br/>
-Apache OpenJPA<br/>
-Toplink<br/>
-EclipseLink<br/>
</p>

<h1>Entity Framework Nedir?</h1>
<p>
.NET platformunda çalışan bir ORM aracıdır.<br/>
Nesne tabanlı programlamada veritabanındaki tablolara uygun nesneler oluşturma tekniğini sağlar.<br/>
Veritabanı olarak esnek bir yapıya sahiptir.Örnek olarak MSSQL ile çalışırken direkt olarak Oracle'a geçebilirsiniz.<br/>
<u>Entity Framework 4 farklı yöntem ile geliştirilebilir;</u><br/>
-Model First(Yeni veritabanı)<br/>
-Database First(Var olan veritabanı)<br/>
-Code First(Yeni veritabanı)<br/>
-Code First(Var olan veritabanı)<br/>

<h3><u>Model First</u></h3>
Bu yöntemde Visual Studio üzerinde boş bir model dosyası eklenerek veri tabanı bu model üzerinde tasarlanır.
<h3><u>Database First</u></h3>
Bu yöntemde hali hazırda var olan veritabanı projeye model dosyası ile bağlanır ve gerekli classlar Entity Framework tarafından oluşturulur.
<h3><u>Code First(New DB)</u></h3>
Bu yöntemde classlar ve mapping kodları yazılımcı tarafından oluşturulur.Daha sonra veritabanı bu classlardan türetilir.
</p>
<h3><u>Code First(Existing DB)</u></h3>
<p>
    Bu yöntemde de classlar ve mapping kodları yazılımcı tarafından oluşturulur.Veritabanı classların ve modellemenin durumuna göre tekrar şekillenebilir.
</p>

<h1>ERM Nedir?</h1>
<p>
Entity Relationship Model,oluşturulacak veritabanı nesneleri arasında ilişki kurarak nesnelerin özelliklerini ortaya koyar.Bir ERM'de 3 temel kavram yer alır;
<br/><u>Entity</u><br/>
Veritabanında oluşturulacak nesneleri temsil eden yapılardır.Veritabanında buna örnek olarak tablolar,programlamada ise sınıflar verilebilir.<br/>
<u>Attribute</u><br/>
ERM içerisindekli entitylerin sahip olduğu her bir alana verilen yapılardır.Veritabanında örnek olarak tablo sütunları verilebilir.<br/>
<u>Relationship</u><br/>
Entityler arasında kurulan fiziksel ve mantıksal bağlantıları temsil eden yapılara denir.ERM diyagramlarında varlıklar arasındaki ilişkiyi tanımlar.
</p>
<h1>Sequelize JS Nedir?</h1>
<p>
Sequelize JS,veritabanını nesnelerle eşleştirir.MySQL,MariaDB,SQLite veya PostgreSQL veritabanlarına kolay erişim sağlayan bir ORM'dir.Mevcut veritabanı şemasını yeni bir sürüme dönüştürebilen çok güçlü geçiş mekanizmasına sahiptir.Ayrıca,model yapısını belirterek veritabanı yapısını oluşturabilen veritabanı senkronizasyon mekanizmaları sağlar.<br/>
Sequelize JS,ORM'in sahip olduğu tüm özelliklere sahiptir.Temel olarak Sequelize JS veritabanı senkronizasyonu,istekli yükleme,çağrışımlar,işlemler ve geçişler için iyi bir desteğe sahiptir.<br/>
Sequelize JS'in bir başka avantajı da test edilebilir kod yazılmasını sağlar.Testleri çalıştırmak için Mocha benzeri çerçeveler kullanılabilir.
</p>