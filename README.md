# 1. Modern Yazılım Geliştirme Pratikleri

Git : Git bir dağıtık versiyon kontrol sistemidir. Dağıtık versiyon kontrol sistemi ana repository nin birden çok klonunu oluşturmak ve klonları ana sistemi koruyarak değişiklik yapmak için kullanılır.

Github : Github git ile yazılan projeler için bir depolama servisidir.

## Git komutları:

git init -> bir dizide git initialize bir local repository oluştururuz.

git clone <link> -> zaten var olan bir repositoryi klonlamak için.

git add -> çalışmamdaki değişiklikleri staging area ya kaydetmemi sağlar.

git commit -> git add komutuyla eklediğim çalışmaları local repositorye kaydetmemi sağlar.

git push -> bilgisayardaki çalışmayı github a yklemek için.

git pull -> github taki çalışmayı bilgisayara çekmek için. 

git branch -> ana projeye dokunmadan klonlayarak aynı projenin projenin farklı versiyonlarını üretmek.

git merge ->sahip olunan branchleri birleştirmek.

Merge Conflict: aynı projenin aynı satrılarında farklılıklar olması ve git in hangisini kullanacağına karar verememesi. Sorunu bulmak için ilk önce git status yazılır. Çıktıda unmerged paths olanlar çakışanlardır. Dosyayı düzenledikten sonra add ile değiştirilen dosyaların düzelmiş olduğunu gite bildirin ve commitle merge işlemini bitirin.

CI: Yazılan kodların merkezi bir depoda (github gibi) sürekli test edilmesi.

CD: CI ı geçen kodun test edilip hazır hale geldiği ve sunuculara dağıtıldığı süreç.

Azure DevOps ve Github Actions : süreçleri otomatikleştirmek için (CI/CD) kullanılan 2 popüler araç. 

 

## SDLC Aşamaları:

- Planlama : Projenin genel hatları, amacı , kullanılabilecek kaynaklar ve zaman belirlenir.

- Analiz : Kurulacak sistemin müşteri isteğine göre gereksinimlerinin bulunması.

- Geliştirme : Sistemin kodlaması yapılır.

- Test : Yazılım kısmında hata olup olmadığına bakılır.

- Dağıtım: Testi geçen ürünler son kullanıcıya sunulur.

- Bakım: Hali hazırda kullanılırken ki sorunları çözmek ve yeni güncellemeler için.

Agile : Gelişimlere karşı dinamik olan sürekli çalışan yazılımlar teslim etmeyi hedefleyen bir yönetim felsefesi.

Kanban: Bir tür agile framework iş yönetimi için görsel bir yöntem.

Scrum: Yine bir tür agile framework sprint planlaması yapılır ,işler seçilir. Günlük scrum toplantıları yapılır ilerleme kontrolü için  .Scrum bitince değerlendirme yapılır.

# 2.NET Ekosistemi

.NET microsoft tarafından oluşturulmuş çapraz platformlara açık , open source bir yazılım geliştirme platformu. İlk olarak 2002 yılında .NET framework ismiyle çıkmış ve gelişerek Windows macOS ve linux ve mobilde çalışan modern bi yapı olan .NET Core a dönüşmüş ve sonrasında birleşik .NET platformuna dönüşmüştür.

Amacı: Web, mobil ,desktop ,cloud ve IoT ve benzeri bir çok platformda oramı ve kütüphaneleri sunar ana dili C# tır.

			Platform			yapı		performans		kullanım alanı

.NET framework 	Windows				closed source	yavaş			legacy uygulamalar

		

.NET Core		Windows, Linux ve macOS 		open source	hızlı			mikro servisler, cloud 											tabanlı sistemler ve modern 											web API’lar

.NET 7/8		Windows, Linux ve macOS 		open source 	her güncellemede daha hızlı	kurumsal projeler, yapay 											zeka uygulamaları ve yeni 											modern projeler

## Senkron ve Asenkron Programlama

Senkron programlama işlemlerin sıralı bir şekilde çalıştığı programlama türüdür. Kolay takip edilir ama işlemler birbirlerini bloklayabilir ve bir işlem uzun sürerse diğer işlemler onu beklemek zorundadır bu da efficiency’yi kötü etkileyebilir.

Asenkron programlama işlemlerin birbirini beklemeden aynı anda çalışabildiği programlama türüdür. İşlemler birbirinden bağımsız şekilde çalışır. Bu programın performansını arttırsa da takip edilmesi oldukça karmaşık hale gelebilir.

- Async : Bir metodun asenkron çalışacağını compiler’a bildiren işaret.

- Await : Asenkron işlemi beklerken diğer işlerin yapılmasını sağlar ve ana sistemi bloke olmaz.

- Task , Task<T> : Gelecekte tamamlanacak asenkron bir işlemi gösterir Task return vermezken Task<T> t tipine return verir.  

	ConfigureAwait(false) : Asenkron işlem tamamlandıktan sonra başladığı iş parçacığına 	dönmek yerine boşta olan iş parçacıklardan devam eder deadlockları engellemek için 	kullanılır.

	“=>” C# ‘ta anonim methodlar için kullanılır.

	Fex: Func<int,int> kareAl = x => x * x; 

	 

	Ayrıca Bodided yöntemi içinde kullanılır return ortadan kalkar

	Fex: public int Topla(int a + int b) => a + b;

	

dotnet –info :  .NET sürümünü ve ortamın detaylarını  gösterir.

- Product info = Kullanılan sürümü gösterir.

- Runtime environment = işletim sistemini gösterir

- .NET Run times Installed = .NET çalışma zamanlarını gösterir.

- Global.json files = Directory içerisinde bir sürüm kuralı var mı ona bakar  yoksa son sürüm kullanılır.

# 3.Backend Geliştirme Temelleri

Frontend vs Backend : Frontend bir web sitesi veya uygulamanın gözüken tarafıdır ,etkileşime girdiği arayüz. Backend ise uygulamanın veya web sitesinin görünmeyen ama sitenin çalışması ,güvenlik ,veri saklama ve benzeri fonskiyonların bulunduğu altyapıdır.

Web sunucusu, API nedir ? API türleri : Web sunucusu, uygulamaların ve web sitelerinin internet üzerinden kullanıcıların ulaşmasını sağlayan donanım ve yazılım bütünüdür. API ise farklı yazılımların belirli kurallar içerisinde veri alışverişi yapmasını sağlar.

## Kullanım Amaçlarına göre API türleri:

- Public: Tüm geliştimecilere açıktır.

- Private: Sadece şirketlerin kendi yazılımcılarının ulaşabildiği gizli sistemlerdir.

- Partner: İş ortaklarının beraber erişebildiği ortak sistemlerdir.

## Protokol ve Mimarilerine göre API türleri:

- REST: HTTP protokolü üzerinde çalışan esnek yapılıdır veri formatı JSON dır.

- SOAP: Kurumsal düzeyde tercih edilen güvenlik standartları yüksek katı kurallı XML tabanlı bir protokol.

- GraphQL: İstemcinin istediği veriyi ona ulaştırmakla görevli bir API.

- gRPC: Işık hızında performans veren gerçek zamanlı veya low latency isteyen işlerde kullanılan API.

## HTTP nedir ?

İstemci ve sunucu arasında veri işlemi sağlayan temel iletişim protokolü.

## HTTP methodları:

- GET: sunucudan veri veya kaynak istemek için kullanılır.

- POST: sunucuya veri veya kaynak göndermek için kullanılır.

- PUT: sunucudaki kaynağı değiştirmek veya oluşturmak için kullanılır.

- DELETE: sunucudaki bir kaynağı silmek için kullanılır.

## RESTful Servislerin çalışma mantığı:

RESTful bir API’ın REST prensiplerine uygun yazılması.

Prensipler:

- Client – Server independency : İstemci ve sunucu birbirinden tamamen bağımsız çalışır. Bu sayede ikiside birbirinden ayrı bir şekilde güncellenebilir ve birbirlerini alakadar etmez.

- Stateless : Sunucu , istemciyle alakalı hiçbir şeyi hatırlamaz ve işlemi gerçekleştirmek için bütün bilgileri sunması gerekir.

- Cacheability: Sunucu , gönderdiği cevapların önbelleğe alınıp alınmayacağını belirler.

- Uniform Interface: Kaynaklara erişmek için bütün sistemlerde standart bir sözleşme kullanılır HTTP methodları.

- Layered System: İstemci son sunucuya mı yoksa bir aracı sunucuya mı bağlandığını bilmez yani her katman sadece tek bir katman biliyor. Bu sayede load-balancing belirli securty policyler firewall gibi güvenlik duvarlarına olanak sağlıyor.

- Code on Demand: Sunucu işlemciye kullanılabilir bir kod yollayarak işlemcinin fonskiyonunu kısa süreli de olsa genişletebilir. Bu prensip tek opsiyonel olandır.

## JSON veri formatı ve kullanım amacı

JSON veri formatı ve kullanım  amacı: JSON farklı programlama dilleri arasında veri transferi yapmak için kullanılan basit bir metin formatı.

Fex:

{

“isim”	 : “emre”,

“hobiler” : [“gezmek”,”tenis”],

“yaş” : 21

}

## REST vs SOAP , GraphQL

Rest HTTP üzerinde çalışır SOAP ise XML üzerinden ayrıca REST daha rahattır kullanım ve anlama olarak.

GraphQL ise bir sorgu dilidir istemcinin sadece ihtiyacı duyduğu veriyi talep etmesini sağlar.

# 4 .ASP.NET

ASP.NET vs ASP.NET Core:

ASP.NET , .NET platformu üzerinde çalışan bir web framework, ASP.NET Core ise .NET Core ve .NET7/8 üzerinde çalışan bir web framework.

// Saf .NET Core — web yok, sadece C#

var sayilar = new List<int> { 1, 2, 3 };

Console.WriteLine(sayilar.Sum());

// ASP.NET Core — web var

var builder = WebApplication.CreateBuilder(args);

var app = builder.Build();

app.MapGet("/merhaba", () => "Merhaba Dünya!");

app.Run();

Yani .NET Core üzerine yazılmış bir web katmanı HTTP isteklerini karşılar , routing yapar, middleware zinciri çalıştırır.

ASP.NET vs ASP.NET Core farkı da .NET framework, .NET Core ve .NET 7/8 arasındaki farklılık gibi performans ve kullanım alanı olarak ilerdedir.

## MVC nedir nasıl çalışır:

Model-View-Controller en çok kullanılan yazılım mimarisi  şablonudur. HTML döndürür.

- Model katmanı: veriyi ve iş mantığını temsil eder.

- View : Kullanıcı arayüzü HTML

- Controller : Model ve View arasındaki koordinatör

## Middleware nedir nasıl çalışır:

Middleware ara yazılım anlamına geliyor. Yani kullanıcının requesti ve gelecek olan response arasındaki yazılım.(Pipeline)

Middleware ‘ ı kullanabileceğim yerler:

- Yönlendirme 

- Kimlik doğrulama

- Yetkilendirme

- Log

## Middleware Metotları

  - Run(): Bu method kısa devre oluşturur ve pipeline üzerindeki işlem durur.

  - Use(): Bir sonraki middlewear a ulaşmak için kullanılır.

  - Map(): Middlewear ı belirler  URL ‘ ye erişmek için kullanılır.

## Dependency Injection

Dependency Injection: Bir class ın ihtiyaç duyduğu nesneden bağımsız hareket edebilmesini sağlar bunu nesneleri dışardan alarak bunu başarır.

DI olmadan:

public class SiparisServisi

{

    private EmailServisi _email;

    public SiparisServisi()

    {

        // Kendi bağımlılığını kendisi oluşturuyor

        _email = new EmailServisi();

    }

    public void SiparisOlustur()

    {

        _email.Gonder("Siparişiniz alındı");

    }

}

Bu kodun 3 problemi var:

SiparisServisi, EmailServisi'ne sıkı sıkıya bağlı. EmailServisi değişirse SiparisServisi de değişmek zorunda. Test yazarken gerçek email gönderimi engellenemiyor. Farklı bir email servisi (SMS, push notification) kullanmak istersen kodu değiştirmek zorundasın.

// Önce bir arayüz tanımla

public interface IEmailServisi

{

    void Gonder(string mesaj);

}

// Gerçek implementasyon

public class EmailServisi : IEmailServisi

{

    public void Gonder(string mesaj)

    {

        Console.WriteLine($"Email gönderildi: {mesaj}");

    }

}

// SiparisServisi artık dışarıdan alıyor

public class SiparisServisi

{

    private readonly IEmailServisi _email;

    // Constructor injection — bağımlılık dışarıdan verildi

    public SiparisServisi(IEmailServisi email)

    {

        _email = email;

    }

    public void SiparisOlustur()

    {

        _email.Gonder("Siparişiniz alındı");

    }

}

## Startup.cs ve Program.cs nedir: İkiside ASP.Net Core uygulamasının başlangıç dosyalarıdır.

Startup.cs NET5 öncesi bir yaklaşım Configure Serviceleri DI container kaydeder. Configure ise middle wearpipeline kurar programcs ise sadece bu sınıfı çağıran birkaç satırlık bir host koduydu.

Sonrasında startup.cs tamamen ortadan kalktı : 

builder.Services.* = Servis kaydı (DI)

app.Use*() / app.Map* = () Middleware ve endpoint

app.Run()

Tek dosyalı sıralı yürütme oldu.

## Katmanlı Mimari: Küçük çaplı projeler için.

- Presentation Layer: Kullanıcı ile etkileşimli olan katman asıl amacı kullanıcı verilerini business ve data layer a aktarmak.

- Business Layer: iş kuralları yazılır sadece toplam tutar hesapla, izin var mı benzeri

- Data Access Layer: Veri tabanı ile konuşma.

- Data Layer:Gerçek veri deposu.

## Patternler :

- Service Pattern : İş katmanında yer alır presentation katmanındaki verilerle business kurallarını çalıştırır ve data accessle işlemleri tamamlar.

- Repository Pattern : Data access te yer alır işlemleri soyutlar ve business layerın bağımsız çalışmasını sağlar.
<img width="1057" height="832" alt="image" src="https://github.com/user-attachments/assets/ddceda05-2ba3-4cc3-850e-c7b5d5ed9952" />

## Clean Mimari: Kurumsal işler için.

Domain Katmanı: En içteki katmandır. İş kurallarını (Business Rules) ve Entity'leri içerir. Başka hiçbir katmandan bağımsızdır 

- Application Katmanı: Domain katmanını kullanarak iş akışlarını koordine eder 

- Infrastructure Katmanı: Veritabanı bağlantıları, dış servisler (API'ler, mail gönderimi) ve framework detaylarını içerir.

- API (Presentation) Katmanı: En dış katmandır. HTTP isteklerini alır ve Application katmanındaki Use Case'leri tetikler.

## Bağımlılıkların Dışa Akması İlkesi (Dependency Inversion / The Dependency Rule)

Clean Architecture'ın kalbidir. Bağımlılıklar her zaman içe (Domain/Application yönüne) doğru olmalıdır.

- İç katmanlar dış katmanları (örneğin veritabanını) kesinlikle tanımaz.

- Dış katmanlar, iç katmanlardaki Interface'leri implemente eder.

- Bu sayede veritabanı teknolojisini  veya UI framework'ünü değiştirmek, çekirdek iş kurallarınızı etkilemez.
<img width="1097" height="812" alt="image" src="https://github.com/user-attachments/assets/0e7a86cc-4a15-4efe-8d61-af2ae9d5acd8" />

# 5.Veritabanı ve ORM

## SQL nedir

İlişkisel bir veri tabanlarıyla konuşmak için kullanılan standart bir dildir. SQL veri tabanları satır ve sütunlardan oluşan tablolar halinde verileri saklar. Şema esneklği oldukça düşüktür.

NoSQL: ilişkisel olmayan daha esnek veri tabanlarıdır.

ORM(Object Relational Mapping): OOP ve SQL arasında iletişim sağlar. SQL sorguları yazmak yerine , tabloları nesneler ve sınıflar üzerinden yönetmemizi sağlar. Kodu değiştirmeden altyapıyı değiştirebiliriz.

Entity Framework Core(EF Core): Microsoftun geliştirdiği open source bir ORM  C# ve LINQ kullanır.

- Code First: Önce C# yazarsın  EF bunu inceleyerek SQL tablosunu kendi oluşturur.

- Database First: Veeri tabanından C# üretir.

DbContext nedir: EF Core ile veri tabanı arasındaki bağlantıyı sağlar — sorgu çalıştırma, değişiklik takibi, transaction yönetimi ve bağlantı açıp kapatma işlemlerin tamamını yönetir. 

DbContext  SaveChanges() yazılana kadar hiç birşeyi veri tabanına yazmaz o sırada nesneleri şu durumlardan biriyle takip eder:

- Added -> Insert bekliyor

- Modified -> Update bekliyor

- Deleted -> Delete bekliyor

- Unchanged -> Değişiklik yok

- Detached -> Takip edilmiyor



## LINQ: C# dilinde SQL sorgularını programlama dilinden çıkmadan yazmamızı sağlar.

LINQ iki farklı yazıma sahiptir:

- Query Syntax
<img width="553" height="237" alt="image" src="https://github.com/user-attachments/assets/55bbfa40-9c7a-49c0-a698-75ed67a04f51" />

Method Syntax																											
<img width="477" height="276" alt="image" src="https://github.com/user-attachments/assets/42e37241-4ffa-42fb-b2c7-9b86042f9f4f" />
En çok kullanılan LINQ ifadeleri: 

- Where() = belirtilen bir koşula uyan verileri filtreler

-  var sonuclar = sayilar.Where(s => s > 10);

- Select() = özellik seçer veya veri dönüştürür

-  Sadece adları seçerek string tipinde yeni bir liste oluşturur :

- var isimler = personeller.Select(p => p.Ad).ToList(); 
// İsim ve Soyismi birleştirip yepyeni isimsiz (anonymous) bir tip oluşturur:
var ozetBilgi = personeller.Select(p => new {
 TamAd = $"{p.Ad} {p.Soyad}",
 Yas = 2026 - p.DogumYili
}).ToList();

- ToList() = verileri list veri tipine dönüştürür.

- FirstOrDefault() = where gibi ama liste yerine verilen şarta uyan ilk datayı döner

- OrderBy() / OrderByDescending() = Verileri artan veya azalana göre sıralar

- var siraliListe = ogrenciler.OrderBy(o => o.Yas);

- Any() = koleksiyonda en az bir elemanına koşula uyup uyumadığını kontrol eder true veya false döner.

- bool varMi = ogrenciler.Any(o => o.Notu < 50);

- Count() = Koleksiyondaki veya belirtilen koşulu sağlayan elemanların toplam sayısını verir.

- int toplam = ogrenciler.Count();

-  GroupBy = Verileri belirli bir özelliğe göre gruplar .

- var grupluListe = ogrenciler.GroupBy(o => o.Sinif);

- Distinct  = koleksiyonda yinelenenleri siler
var tekilSayilar = sayilar.Distinct();

## Temel SQL sorguları

- SELECT : (read) verileri filtreleyerek veya doğrudan listeler

- SELECT ad, soyad, sehir FROM Kullanicilar;
SELECT * FROM Kullanicilar WHERE sehir = 'İstanbul';

- INSERT : (create) tabloya yeni satırlar ekler

- INSERT INTO Kullanicilar (ad, soyad, sehir, yas) 
VALUES ('Ahmet', 'Yılmaz', 'Ankara', 30);

- UPDATE: (güncelle) mevcut verileri değiştirir

- UPDATE Kullanicilar 
SET sehir = 'İzmir', yas = 31 
WHERE id = 5;

- DELETE: (sil) tablodan kayıt siler.

	

	DELETE FROM Kullanicilar WHERE id = 5;

# 6. Güvenlik ve Performans

## Authentication : kimlik doğrulama

Authorization: yetkilendirme

                                                                                                                                        

## JWT : json web token json formatında authentiaction ve authorization için kullanılan bir standart.

Stateless tır tüm gerekli bilgileri token içinde tutar sunucu kullanıcının kimliğini doğruladıktan sonra bilgileri şifreleyerek bir JWT üretir. Sunucu bu tokeni istemciye gönderir ve istemcinin her isteğinde HTTP başlığına bu tokeni ekler sunucu gelen tokeni doğrularsa işlem gerçekleşir.

Üç bileşenin özeti:

1. Header — Token tipi ve kullanılan imzalama algoritması gibi iki temel bilgiyi içerir. Örneğin { "alg": "HS256", "typ": "JWT" }.

2. Payload (Claims) — Kayıtlı claim'leri içerir: iss (issuer), exp (expiration), sub (subject), aud (audience). Bunların yanı sıra çalışan rolü gibi özel (custom) claim'ler de eklenebilir. 

3. Signature — İmza, başlık ve payload'ı şifreleme algoritmasıyla imzalayarak token'ın bütünlüğünü sağlar. Token'ın herhangi bir kısmı değiştirilirse imza doğrulama başarısız olur. 

OAuth ve OAuth2.0 : Kullancının şifrelerini 3. taraflar tarafından alınmadan bir servisteki verilerin başka servislere bağlanmasını sağlar. OAuth2.0 farkı ise kimlik doğrulaması yapmadan sadece authorization yapmasıdır.

OpenID ve OpenID Connect: Bir kullanıcının birden fazla web sitesine tek bir hesap bilgisiyle erişebilmesini sağlayan bir authentication protokolüdür. OpenID Connect ise OAuth2.0 üzerine inşa edilmiş halidir. Authenticationu OAuth2.0 ile yapar ve kullanıcının kim olduğunu anlamamızı sağlar.

OpenIddict: ASP.NET Core  uygulamalarında ve projelerinde Authentication ve Authorization yapmak için kullanılan açık kaynaklı bir kütüphanedir.

## Performans Arttırımı :

- AsNoTracking = Entity Framework tarafından performans optimizasyonu için tasarlanmış bir fonsiyondur. Sorgu da elde edilen nesnelerin takip mekanizmasını kırar ve gereksiz depolanmadan kurtulur.

- IAsyncEnumerable<T>: Basit task yöntemleri tek seferlik işlemler için yeterli olsa da uzun devamlı işlemler için yetersiz kalır. IAsyncEnumerable verileri asenkron ve parça parça işlememizi sağlar. Yani verilerin hepsini yüklemektense yüklenen ve hazır olanları işler.

- Caching : Sürekli kullanılan verileri önbelllekte muhafaza eder. Veri tabanı sorgulamasına gerek kalmaz.

- Redis : Distributed Caching olan veriyi RAM üzeride key-value şeklinde tutan büyük bir veri deposu.

- Profiling : Uygulamanın nerelerde yavaşladığını SQL sorguları ile bulmak için. 

## OWASP Top 10 : TOP 10 güvenlik açığı

- Broken Access Control : İzni olmayan bir kullanıcının gizli bilgileri görme ihlali.

- Crytographic Failures : Saklanan hassas veriyi basit filtreleme.

- Injection :  Kötü amaçlı SQL gibi talimat verir gibi içeri sızan kodlar.

- Insecure Design : Tasarım ve mimari kusurlarınhata mesajları temizlenmezse içerisinde bulundurdukları hassas veriler kötü niyetle kullanılabilir.

- Security Misconfiguration : Eğer güvenlik süreçleri  ile uyumlu değilse güvenli bir şekilde yapılandırılmalıdır yoksa security misconfiguration olur.

- Vulnerable and Outdated Components : Sistem de kullanılan güvenlik bileşenlerinin güncel veya destekli olmaması.

- Identification and Authentication Failures : Zayıf şifre politikaları, ikincil doğrulamaların kullanılmaması ve kötü oturum süreleri kimlik doğrulama saldırılarına karşı zayıflatır.

- Software and Data Integrity Failures : Otomatik güncellemelerin nereden yapıldığı ve yeteri kadar güvenli olup olmadığı önemli çünkü CI/CD pipeline içerisine istenmeyen yeni bir iş akışı eklenebilir.

- Security Logging adn Monitoring : monitor ve loglama yaparak sistem sızmalarını tespit etmek.	

- Server Side Request Forgery : İstekleri sanki mağdur sunucunun istekleriymiş gibi yollamak. Bunun çözümü ise dış kaynaklardan sadece bazı ip ve host adreslerine izin vermek.

# 7.Logging ve Hata Yönetimi

## Neden loglama yapılır?

Neden loglama yapılır ve loglama nedir : Loglama sistwmin çalışırken ki davranışlarını kaydetmesidir hata , bilgi , uyarı gibi. Log seviyesi bu kayıtların önem derecesini belirler (Trace < debug < information < warning < error < critical). ASP.NET Core yerleşik olarak yapılandırılabilir, hızlı loglama altyapısına sahiptir. Loglama sorun gidermek için yani beklenmeyen hataların kökünü bulmak için kullanılır , kullancıların davranışlarının izlerini tuttar , istek sürelerini ölçerek performans izler ve problemli yerleri bulur , yetkisiz erşimleri ve başarısız giriş işlemleri loglanarak güvenlik sağlar.

## Log seviyelerinin anlamları:

- Trace = geliştirme aşamasında hata detect içindeki

- debug = geliştirme aşamasında akışı izlemek için

- information = sistemdeki genel akışı gösterir

- warning = sistem çalışmaya devam eder ama olası sorunları gösterir

- error = başarısız işlemler de oluşan hataları gösterir

- critical = sistemin çökmesine sebebiyet verecek acil durumlardır

### ASP.NET Core logging altyapısı : ASP.NET Core arka planda yüksek performanslı loglama destekleyen ILogger kullanır. Bu loglama sağlayıcı dışında bağımsız kod yazmamıza olanak sağlar.

ILogger<T> arayüzü sınıflara Dependency  Injection ile yazılır

Örnek Kullanım:

using Microsoft.AspNetCore.Mvc;

[ApiController]

[Route("api/[controller]")]

public class ProductsController : ControllerBase

{

    private readonly ILogger<ProductsController> _logger;

    // ILogger, Dependency Injection ile enjekte ediliyor

    public ProductsController(ILogger<ProductsController> logger)

    {

        _logger = logger;

    }

    [HttpGet("{id}")]

    public IActionResult GetProduct(int id)

    {

        _logger.LogInformation("ProductsController GetProduct metodu çağrıldı. İstenen ID: {ProductId}", id);

        if (id <= 0)

        {

            _logger.LogWarning("Geçersiz ürün ID'si ile istek yapıldı: {ProductId}", id);

            return BadRequest("Geçersiz ID");

        }

        // Örnek bir hata simülasyonu

        try

        {

            // İş mantığı kodları

        }

        catch (Exception ex)

        {

            _logger.LogError(ex, "Ürün getirilirken bir hata oluştu. ID: {ProductId}", id);

            return StatusCode(500, "Sunucu hatası");

        }

        return Ok();

    }

}

Global Expection Handler nasıl kullanılır : her işlem için try catch yazmak yerine merkezi bir expection handler kullanılır

# 8.Yazılım Geliştirme Prensipleri

## SOLID :

- S : Single Responsibility Principle : Her sınıfın ve method tek bir amaca hizmet etmeli

- O : Open/Closed Principle : Bir sınıf veya fonksiyon gelişime açık değişime kapalı olmalı 

- L : Liskov Substitution : Alt sınıflarda oluşturulan nesneler , üst sınıf nesnelerin yaptığı her şeyi yapabilmeli

- I : Interface Segregation : Bir interfacei impelement eden sınıf o interfacein tüm fonskiyonlarını kullanmıyorsa, kullanılmayan fonskiyonlar farklı bir interface e konulmalı 

- D : Dependency Inversion : Yüksek seviyeli modül sınıfların düşük modüllere bağımlı olmasındansa her ikisininde abstract classlara bağımlı olması lazım.

## Design Pattern

Design Pattern: object oriented yazılımlarda  yaygın olarak karşılaşılan sorunlar için hazırlanmış basma kalıp kodlardır. 3 e ayrılırlar.

- Creational design : nesnelerin nasıl yaratılacağı hakkında öneriler sunar.

- Structual : Farklı objelerin bir bütün olması

- Behavioral : Objeler arası iletişim kurulması

ÖRNEKLER

- Singleton: Bir sınıftan sadece bir adet nesne oluşturulmasını ve nesneye global erişimi garanti eder. Birden fazla örneği engellemiş olur ve uygulamanın her yerinden erişilebilir.

- Repository: Data Access ve Business Logic arasında net bir ayrım sağlar ve iş mantığını değiştirmeden farklı verileri destekler.

- Factory: Nesne oluşturmayı new ile yapmak yerine işlem bir factory sınıfı üzerinde gerçekleşir. Hangi sınıfın oluşturulacağı çalışma anında karar verilir.

## Clean Code

Clean Code nedir ve neden önemli: Okunabilir ve temiz kod. Daha az hata , hızlı geliştirme ve uyum sağlar.

1. Anlamlı ve Açıklayıcı İsimlendirme
İsimler, değişkenin veya fonksiyonun amacını açıkça belli etmelidir. Kısaltmalardan ve kafa karıştırıcı isimlendirmelerden kaçınılmalıdır.

-  Kötü: int d; (Gün cinsinden süre mi, mesafe mi belli değil)

- İyi: int daysSinceLastUpdate;

2. Fonksiyonların Tek Sorumluluğu Olmalı (SRP)
Bir fonksiyon sadece ve sadece tek bir işi yapmalıdır. Fonksiyon adları fiil olmalı ve küçük tutulmalıdır.

-  Kötü: Kullanıcıyı veri tabanından bulup, şifresini değiştirip, mail gönderen tek bir büyük fonksiyon.

- İyi: İşlemleri findUser(), updatePassword(), sendEmailNotification() şeklinde üç küçük fonksiyona bölmek.

3. "Magic Number" (Sihirli Sayılar) Kullanmamak
Kod içerisinde doğrudan kullanılan sayılar yerine, bu sayıların ne anlama geldiğini belirten sabitler (constant) kullanılmalıdır.

- Kötü: if (status == 4) { ... } (4 ne anlama geliyor?)

- İyi:

- java

- const int USER_STATUS_ACTIVE = 4;

- if (status == USER_STATUS_ACTIVE) { ... 

## Yazılım Mimari Desenleri:

- Layered = Basit ve düşük maliyetli geleneksel CRUD işlemlerinin yoğun olduğu uygulamalar. Karmaşık olmayan projelerde tercih edilir. 4 katmana ayrılır. 

- Presentation katmanı	Business katmanı 	Kalıcılık Katmanı	Veritabanı Katmanı

- hızlı geliştirmelerde kullanılır, startup, küçük ekip vs

- Clean = İş kurallarının yoğun olduğu uzun ömürlü ve değişime açık projeler Dependency Inversion kullanır

- orta büyük , uzun ömürlü projelerde

- Hexagonal = çok fonksiyonlu iş kurallarını içeren domain etrafında iletişim için portlar bulunur bu portlar aracılığylada adapörler dış dünya  ile iletişim sağlar her bileşen bağımsız olarak test edilebilir ve oldukça esnektir

- çok entegrasyon noktası bulunan senaryolarda

- Micorservices = çok büyük ölçekli bir yazılımın bölünüp farklı ekiplerin aynı anda başka modüller üzerinde çalıştığı ve diğer ekiplerle API üzerinden iletişim sağladığı mimari model. Dayanıklı ve durdurulmaya gerek duymadan geliştirilebilen bir model.

- Büyük ekiplerin olduğu bağımsız çalışılması gereken çok yoğun trafikli büyük projeler

- Event Driven = Servislerin asenkron bir şekilde çalıştığı ve gerçek zamanlı bildirimlere sahip olan istek yanıt mantığına dayalı model.

	Asenkron akışların yoğun olduğu e-ticaret vs
