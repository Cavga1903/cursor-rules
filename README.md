# Cursor Rules - AI Development Rules Collection

Bu repository, Cursor IDE için geliştirilmiş AI development rules dosyalarını içerir. Bu kurallar, AI asistanlarının (Cursor, Claude, Copilot) kodunuzu daha iyi anlaması ve daha tutarlı öneriler sunması için optimize edilmiştir.

## 📋 İçindekiler

### Core Rules (Her Zaman Uygulanan)

- **`roadmaprules.mdc`** - Master roadmap rules, öncelik sırası ve epic durumu takibi
- **`development-workflow.mdc`** - Sistemsel kod yazma süreci (PRE-CODE, DURING-CODE, POST-CODE)
- **`reactrules.mdc`** - React performans optimizasyon kuralları (Vercel Best Practices)
- **`ai-optimization.mdc`** - AI context window optimizasyonu (250 satır limiti, tek component per dosya)
- **`start-guide.mdc`** - Otomatik başlangıç ve devam etme sistemi
- **`typescript-rules.mdc`** - TypeScript best practices, type safety, strict mode
- **`security-rules.mdc`** - Güvenlik best practices, authentication, authorization, input validation
- **`testing-rules.mdc`** - Test best practices, test patterns, coverage guidelines
- **`error-handling-rules.mdc`** - Hata yönetimi patterns, error recovery strategies
- **`accessibility-rules.mdc`** - Erişilebilirlik guidelines, WCAG compliance, ARIA patterns
- **`git-workflow-rules.mdc`** - Git workflow, commit conventions, branch strategy
- **`documentation-rules.mdc`** - Dokümantasyon standartları, JSDoc, code comments

### Project-Specific Rules

- **`bmad-context-checker.mdc`** - BMad context kontrol sistemi (kategorize edilmiş)
- **`mvprules.mdc`** - MVP kuralları ve UI consistency (projeye özel)

## 🚀 Kurulum

### Yöntem 1: Symlink (Önerilen)

Mevcut projenizde `.cursor/rules/` klasörünü bu repo'ya symlink olarak bağlayın:

```bash
# Mevcut rules klasörünü yedekle (opsiyonel)
mv .cursor/rules .cursor/rules.backup

# Symlink oluştur
ln -s /path/to/cursor-rules .cursor/rules
```

### Yöntem 2: Git Submodule

Projenize git submodule olarak ekleyin:

```bash
# Proje root dizininde
git submodule add https://github.com/your-username/cursor-rules.git .cursor/rules
git submodule update --init --recursive
```

### Yöntem 3: Manuel Kopyalama

```bash
# Proje root dizininde
cp -r /path/to/cursor-rules/* .cursor/rules/
```

## 📁 Proje Yapısı

```
cursor-rules/
├── README.md
├── LICENSE
├── CHANGELOG.md
├── VERSION
├── CONTRIBUTING.md
├── SETUP.md
├── .gitignore
├── .gitattributes
├── .github/
│   └── workflows/
│       └── ci.yml           # CI/CD workflow
├── templates/
│   ├── mvprules.template.mdc      # MVP rules template
│   └── roadmaprules.template.mdc   # Roadmap rules template
├── roadmaprules.mdc          # Master roadmap rules
├── development-workflow.mdc   # Development workflow
├── reactrules.mdc            # React best practices
├── ai-optimization.mdc       # AI optimization
├── start-guide.mdc           # Start/continue guide
├── typescript-rules.mdc      # TypeScript best practices
├── security-rules.mdc        # Security best practices
├── testing-rules.mdc         # Testing best practices
├── error-handling-rules.mdc  # Error handling patterns
├── accessibility-rules.mdc   # Accessibility guidelines
├── git-workflow-rules.mdc    # Git workflow & conventions
├── documentation-rules.mdc   # Documentation standards
├── bmad-context-checker.mdc  # BMad context checker
└── mvprules.mdc              # MVP rules (projeye özel)
```

## 🔧 Kullanım

### Yeni Proje İçin Uyarlama

1. **Template Dosyalarını Kullan:**
   - `templates/mvprules.template.mdc` - MVP rules template'ini kopyalayıp özelleştirin
   - `templates/roadmaprules.template.mdc` - Roadmap rules template'ini kopyalayıp özelleştirin

2. **Proje-Specific Rules'ı Güncelle:**
   - `mvprules.mdc` - Proje adını, MVP kurallarını güncelle
   - `roadmaprules.mdc` - Proje roadmap'ini güncelle
   - `bmad-context-checker.mdc` - BMad klasör yapısını güncelle (eğer kullanıyorsanız)

2. **Roadmap Entegrasyonu:**
   - `roadmaprules.mdc` dosyasındaki roadmap path'ini güncelle:
     ```markdown
     **Roadmap Dosyası:** `_bmad-output/planning-artifacts/roadmap.mdc`
     ```
   - Projenizin roadmap yapısına göre güncelle

3. **BMad Entegrasyonu (Opsiyonel):**
   - Eğer BMad kullanmıyorsanız, `bmad-context-checker.mdc` dosyasını kaldırabilir veya devre dışı bırakabilirsiniz
   - `alwaysApply: false` yaparak devre dışı bırakabilirsiniz

### Rule Dosyası Formatı

Her rule dosyası frontmatter ile başlar:

```markdown
---
alwaysApply: true  # veya false
---

# Rule Başlığı

Rule içeriği...
```

## 🎯 Rule Kategorileri

### 1. Always Apply Rules (Her Zaman Uygulanan)

- `roadmaprules.mdc` - Öncelik sırası ve epic durumu
- `development-workflow.mdc` - Kod yazma süreci
- `reactrules.mdc` - React best practices
- `ai-optimization.mdc` - AI optimizasyonu
- `start-guide.mdc` - Başlangıç/Devam sistemi

### 2. Project-Specific Rules (Projeye Özel)

- `mvprules.mdc` - MVP kuralları (projeye özel)
- `bmad-context-checker.mdc` - BMad entegrasyonu (opsiyonel)

## 📚 Rule İçerikleri

### roadmaprules.mdc
- Öncelik sırası (P0 → P1 → P2 → P3)
- Epic durum takibi
- Süreç döngüsü
- Quality gates
- Git commit kuralları

### development-workflow.mdc
- PRE-CODE: Kod yazmadan önce kontrol
- DURING-CODE: Kod yazarken kontrol
- POST-CODE: Kod yazdıktan sonra kontrol
- Quality gates checklist

### reactrules.mdc
- Vercel Best Practices entegrasyonu
- Waterfall elimination
- Bundle optimization
- Re-render optimization
- Route-based code splitting

### ai-optimization.mdc
- Context window optimizasyonu
- 250 satır limiti
- Tek component per dosya
- ESLint kuralları

### start-guide.mdc
- "Başla" komutu işleme
- "Devam et" komutu işleme
- Senaryo bazlı başlangıç
- Otomatik öncelik belirleme

### typescript-rules.mdc
- Type safety kuralları
- Strict mode kullanımı
- Type inference best practices
- Utility types ve generics
- Null safety patterns

### security-rules.mdc
- Authentication & authorization
- Session management
- Rate limiting
- Input validation & sanitization
- SQL injection prevention

### testing-rules.mdc
- Test piramidi stratejisi
- Unit testing patterns
- Component testing (React Testing Library)
- Integration testing
- Test coverage guidelines

### error-handling-rules.mdc
- Error types ve kategorileri
- Try-catch best practices
- Result type pattern
- Error boundaries (React)
- Error recovery strategies

### accessibility-rules.mdc
- WCAG 2.1 AA compliance
- Keyboard navigation
- ARIA labels & roles
- Color contrast requirements
- Form accessibility

### git-workflow-rules.mdc
- Branch naming conventions
- Conventional commits
- Commit message structure
- Merge strategies
- Code review checklist

### documentation-rules.mdc
- JSDoc comments
- Component documentation
- API documentation
- README standards
- Architecture decision records

## 🔄 Güncelleme

### Symlink Kullanıyorsanız

```bash
cd /path/to/cursor-rules
git pull origin main
```

### Submodule Kullanıyorsanız

```bash
cd /path/to/your-project
git submodule update --remote .cursor/rules
```

## 🤝 Katkıda Bulunma

Detaylı katkı rehberi için [CONTRIBUTING.md](CONTRIBUTING.md) dosyasına bakın.

Kısa özet:
1. Fork yapın
2. Feature branch oluşturun (`git checkout -b feature/amazing-rule`)
3. Değişikliklerinizi commit edin (`git commit -m 'Add amazing rule'`)
4. Branch'inizi push edin (`git push origin feature/amazing-rule`)
5. Pull Request oluşturun

## 📝 Lisans

Bu repository MIT lisansı altında lisanslanmıştır.

## 🔗 Referanslar

- [Vercel Labs React Best Practices](https://github.com/vercel-labs/agent-skills/tree/main/skills/react-best-practices)
- [AI için Optimize Edilmiş Kod Yapısı](https://medium.com/@your-article)
- [Cursor IDE Documentation](https://cursor.sh/docs)

## 📧 İletişim

Sorularınız veya önerileriniz için issue açabilirsiniz.

---

**Son Güncelleme:** 2026-01-19  
**Versiyon:** 1.0.0
