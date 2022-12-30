# zkevm-Node

- zkEVM Düğümü zkEVM Düğümü, Poligon zkEVM Ağını çalıştıran bir düğümün Go uygulamasıdır. Polygon zkEVM ağı hakkında bir protokolün uygulanması olduğundan, onu anlamak esastır, burada protokolün özelliklerini bulabilirsiniz. 

- Sözlük: 

- L1: Toplu akıllı sözleşmelerin konuşlandırıldığı temel blok zinciri. Bu, Ethereum veya Ethereum'un bir test ağıdır, ancak herhangi bir EVM uyumlu blok zinciri olabilir. 

- L2: toplama ağı, diğer adıyla Polygon zkEVM ağı. 

- Toplu iş: zkEVM prover kullanılarak yürütülen/kanıtlanan ve L1'e gönderilen/L1'den senkronize edilen bir grup işlem. 

- Sıralayıcı: İşlemleri seçmekten, bunları belirli bir sıraya koymaktan ve toplu halde L1'e göndermekten sorumlu aktör. 

- Güvenilir sıralayıcı: Özel ayrıcalıklara sahip sıralayıcı, yalnızca bir tane güvenilir sıralayıcı olabilir. Güvenilir sıralayıcıya verilen ayrıcalıklar, onun L1'e uygulanacak partileri tahmin etmesine izin verir. Bu şekilde, L1 ile etkileşime girmeden önce belirli bir sırayı taahhüt edebilir. Bu, hızlı kesinlik elde etmek ve ağ kullanımıyla ilişkili maliyetleri azaltmak için yapılır (daha düşük gaz ücretleri) 

- İzinsiz sıralayıcı: herkes tarafından gerçekleştirilebilen sıralayıcı rolü. Güvenilir sıralayıcıya kıyasla rekabetçi dezavantajları vardır (yavaş kesinlik, MEV saldırıları). Ana amacı, ağa sansür direnci ve durdurulamazlık özellikleri sağlamaktır. Sıra: Güvenilir sıralayıcının durumu güncellemek için L1'e gönderdiği toplu iş grubu ve diğer meta veriler. 

- Zorunlu toplu iş: Durumu güncellemek için izinsiz sıralayıcılar tarafından L1'e gönderilen toplu iş. 

- L2 Bloğu: L1 bloğu ile aynı, ancak L2 için. Bu çoğunlukla JSON RPC arabirimi tarafından kullanılır. Şu anda, tüm L2 Blokları yalnızca bir işlem içerecek şekilde ayarlanmıştır, bu, anında kesinlik elde etmek için yapılır: JSON RPC'nin halihazırda işlenmiş işlemlerin sonuçlarını göstermesine izin vermek için bir toplu işi kapatmak gerekli değildir. 

- Güvenilen durum: Güvenilen sıralayıcı tarafından paylaşılan işlemlerin işlenmesi yoluyla ulaşılan durum. Güvenilir sıralayıcı belirli bir sırayı işleyebileceğinden ve ardından L1'e farklı bir tane gönderebileceğinden, bu durum güvenilir olarak kabul edilir. 

- Sanal durum: Halihazırda L1'e gönderilmiş olan işlemlerin işlenmesi yoluyla ulaşılan durum. Bu işlemler, güvenilir veya izinsiz sıralayıcılar tarafından toplu olarak gönderilir. Bu gruplara sanal partiler de denir. L1 güvenlik varsayımlarına dayandığından bu durumun güvenilir olmadığını unutmayın. 

- Konsolide durum: son sanal parti dizisinin yürütülmesini kanıtlayan bir ZKP (Sıfır Bilgi Kanıtı) göndererek zincir üzerinde kanıtlanmış durum. 

- Geçersiz işlem: işlenemeyen ve durumu etkilemeyen bir işlem. Böyle bir işlemin sanal toplu işleme dahil edilebileceğini unutmayın.
