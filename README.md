# 📘 ILMEQ: Interlinked Ledger Metadata for Educational Qualifications

**ILMEQ** (Interlinked Ledger Metadata for Educational Qualifications), eğitimsel belgelerin merkeziyetsiz, doğrulanabilir ve birbirleriyle ilişkisel biçimde tanımlanmasını sağlayan bir JSON Schema tanımıdır.

Bu şema; diplomalar, transkriptler, tez belgeleri ve diğer akademik belgeler için kriptografik kimlikler tanımlamaya, belgeler arası ilişkiler kurmaya ve belge geçerlilik durumlarını izlemeye olanak tanır.

This paper accepted and will be presented 26-27 August 2025 at ICCCE, Malaysia

Conference Paper Name: A Cryptographically-Linked Metadata Schema for Academic Credential Interoperability: the ILMEQ Model

Conference Name: 2025 10th International Conference on Computer and Communication Engineering (ICCCE)

---

## 📂 Dosya

- `ilmek.schema.json`: JSON Schema 2020-12 standardına uygun olarak hazırlanmış belge şeması.

---

## 🎯 Amaç

Bu şemanın temel hedefleri:

- 📄 Akademik belgelerin **türlerini** ve **durumlarını** standartlaştırmak
- 🔗 Belgeler arasında **ilişki** kurmak (örneğin bir tezin bir diplomaya bağlı olması)
- 🔐 Her belgeye özgü **kriptografik hash** ile bütünlük sağlamak
- 🧾 Belgeye ait tarafları belirtmek (verici ve alıcı DID'ler)
- 📅 Zaman damgaları ile belgelerin yaşam döngüsünü takip edebilmek

---

## 🧱 Örnek Kullanım

```json
{
  "document_id": "doc:diploma:abcd1234efgh5678",
  "type": "Diploma",
  "issuer": "did:example:university001",
  "recipient": "did:example:student567",
  "issued_at": "2024-06-01T12:00:00Z",
  "hash": "sha256:4a6f4f2e8a1f7a8d1c4e1d7e5e8a3b4c5d6e7f8a9b0c1d2e3f4a5b6c7d8e9f00",
  "status": "active",
  "relations": [
    {
      "relation_type": "is_based_on",
      "target_document": "doc:thesis:123abc456def7890",
      "effect_on_target": "linked_validation"
    }
  ]
}
