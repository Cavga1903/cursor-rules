# Kurulum Talimatları

## 🚀 Hızlı Başlangıç

### 1. Remote Repository Oluşturma

GitHub, GitLab veya başka bir git hosting servisinde yeni bir repository oluşturun:

```bash
# GitHub örneği
gh repo create cursor-rules --public --source=. --remote=origin --push
```

Veya manuel olarak:

```bash
# Remote ekle
git remote add origin https://github.com/your-username/cursor-rules.git

# İlk push
git push -u origin main
```

### 2. Mevcut Projeye Entegrasyon

#### Yöntem 1: Symlink (Önerilen - En Esnek)

```bash
# Mevcut projenizde
cd /path/to/your-project

# Mevcut rules'ı yedekle (opsiyonel)
mv .cursor/rules .cursor/rules.backup

# Symlink oluştur
ln -s /Users/tolgacavga/Projects/cursor-rules .cursor/rules

# Kontrol et
ls -la .cursor/rules
```

**Avantajları:**
- ✅ Tek bir kaynak, tüm projelerde güncel
- ✅ Değişiklikler otomatik yansır
- ✅ Her projede ayrı kopya yok

**Dezavantajları:**
- ⚠️ Proje-specific rules için dikkatli olmak gerekir

#### Yöntem 2: Git Submodule

```bash
# Mevcut projenizde
cd /path/to/your-project

# Mevcut rules'ı yedekle
mv .cursor/rules .cursor/rules.backup

# Submodule ekle
git submodule add https://github.com/your-username/cursor-rules.git .cursor/rules

# Initialize
git submodule update --init --recursive
```

**Güncelleme:**
```bash
git submodule update --remote .cursor/rules
```

**Avantajları:**
- ✅ Proje ile birlikte version control
- ✅ Her projede belirli bir commit'e bağlı
- ✅ Team ile paylaşım kolay

**Dezavantajları:**
- ⚠️ Her projede ayrı kopya
- ⚠️ Güncelleme için manuel işlem gerekir

#### Yöntem 3: Manuel Kopyalama

```bash
# Mevcut projenizde
cd /path/to/your-project

# Rules'ı kopyala
cp -r /Users/tolgacavga/Projects/cursor-rules/* .cursor/rules/

# Proje-specific rules'ı güncelle
# mvprules.mdc, roadmaprules.mdc, vb.
```

**Avantajları:**
- ✅ Tam kontrol
- ✅ Proje-specific özelleştirme kolay

**Dezavantajları:**
- ⚠️ Güncellemeler manuel
- ⚠️ Her projede ayrı kopya

### 3. Proje-Specific Rules'ı Güncelleme

#### mvprules.mdc

Proje adını ve MVP kurallarını güncelleyin:

```markdown
# Your Project Name — MVP Rules (LAW)

## (0) MVP North Star
If it doesn't help **your core features**, it is OUT.
```

#### roadmaprules.mdc

Roadmap path'ini güncelleyin:

```markdown
**Roadmap Dosyası:** `_bmad-output/planning-artifacts/roadmap.mdc`
```

Projenizin roadmap yapısına göre güncelleyin.

#### bmad-context-checker.mdc

Eğer BMad kullanmıyorsanız:

```markdown
---
alwaysApply: false  # Devre dışı bırak
---
```

Veya dosyayı kaldırın.

## 🔄 Güncelleme Süreci

### Symlink Kullanıyorsanız

```bash
cd /Users/tolgacavga/Projects/cursor-rules
git pull origin main
```

Tüm projelerde otomatik güncellenir.

### Submodule Kullanıyorsanız

```bash
cd /path/to/your-project
git submodule update --remote .cursor/rules
git add .cursor/rules
git commit -m "chore: update cursor rules"
```

### Manuel Kopyalama Kullanıyorsanız

```bash
cd /path/to/your-project
cp -r /Users/tolgacavga/Projects/cursor-rules/* .cursor/rules/
# Proje-specific rules'ı tekrar güncelle
```

## 📝 Yeni Proje İçin Checklist

- [ ] Remote repository oluşturuldu
- [ ] Mevcut projeye entegre edildi (symlink/submodule/kopya)
- [ ] `mvprules.mdc` proje adına göre güncellendi
- [ ] `roadmaprules.mdc` roadmap path'i güncellendi
- [ ] `bmad-context-checker.mdc` güncellendi veya devre dışı bırakıldı
- [ ] Cursor IDE'de rules'ların yüklendiği kontrol edildi
- [ ] Test: "başla" komutu çalışıyor mu?
- [ ] Test: "devam et" komutu çalışıyor mu?

## 🎯 Best Practices

1. **Symlink kullanın** - En esnek ve güncel kalır
2. **Proje-specific rules'ı ayrı tutun** - `mvprules.mdc` gibi
3. **Roadmap path'ini her projede güncelleyin**
4. **BMad kullanmıyorsanız** - `bmad-context-checker.mdc`'yi devre dışı bırakın
5. **Düzenli güncelleme yapın** - Yeni best practices eklenebilir

## 🔗 İlgili Dosyalar

- `README.md` - Genel bilgiler
- `.gitignore` - Git ignore kuralları
- `.gitattributes` - Git attributes (line endings)

---

**Son Güncelleme:** 2026-01-19
