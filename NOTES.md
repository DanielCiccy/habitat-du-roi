
# Improvement Notes - Habitat du Roi

## 2025-01-29 - Oracle verification and contract updates

### Changes made
- **Oracle verification button**: Added a non-functional Oracle verification button on the legal identity form
- **Contract content update**: Removed paragraph 3.2 about community-validated payment stages
- **Business model clarification**: Habitat du Roi will initially focus on selling feasibility studies to real estate developers

#### 1. Oracle verification implementation
- **Component created**: `OracleVerificationButton.tsx` - Placeholder for future investment capacity verification
- **Integration**: Added to `LegalIdentityForm.tsx` with conditional display
- **UI/UX**: Amber-themed warning section with tooltip explaining future functionality
- **Accessibility**: Disabled state when user data is incomplete

#### 2. Contract content modifications
- **Removed section**: Paragraph 3.2 about community-validated payment stages in both French and English versions
- **Business rationale**: Aligns with initial business model focusing on developer partnerships
- **Cost advantage**: 1% net cost vs current 10% for traditional feasibility studies

#### 3. Business model evolution
- **Initial phase**: Selling feasibility studies to real estate developers
- **Competitive advantage**: Significant cost reduction (1% vs 10%)
- **Market disruption**: Enabling projects that couldn't find traditional feasibility
- **Ecosystem value**: Creating new opportunities for previously unfeasible operations

### Technical implementation details
- **Oracle button**: Tooltip-enabled with Eye icon and development status message
- **Form integration**: Conditional enabling based on user data completeness
- **Contract updates**: Synchronized across French and English versions
- **Numbering adjustment**: Automatic renumbering of remaining paragraphs

### Benefits achieved
- ✅ **Future-ready**: Infrastructure for Oracle integration prepared
- ✅ **Contract accuracy**: Aligned with current business model
- ✅ **User clarity**: Clear indication of upcoming verification features
- ✅ **Development roadmap**: Placeholder for future implementation

### Next steps suggested
1. Implement actual Oracle verification logic
2. Define API contracts for investment capacity validation
3. Integrate with blockchain oracles for automated verification
4. Test user experience flow with real Oracle responses

---

## 2025-01-27 - Dynamic country tables implementation

### Problem identified
- Static tables didn't allow flexible country management
- Non-normalized data according to local standards
- Limited performance with single global table

### Solution implemented

#### 1. Dynamic country tables
- **Naming convention**: `property_demands_{country_code}` (e.g., `property_demands_fr`, `property_demands_us`)
- **Country codes**: ISO 3166-1 alpha-2 (FR, US, CA, DE, etc.)
- **On-demand creation**: Tables automatically created on first user registration

#### 2. SQL functions created
- `create_country_property_demands_table(country_code)` - Dynamic table creation
- `normalize_address_data()` - Address normalization according to national standards
- `get_property_demands_table_name()` - Utility to get table name

#### 3. Updated hooks
- `useCountryPropertyDemands` - New hook for country management
- `usePropertyDemandCountry` - Migration to country system
- `useProjectsMapCountry` - Adaptation to load by country

#### 4. Data normalization
- **Postal codes**: Validation according to national format (5 digits FR, 5+4 US)
- **Cities**: Smart capitalization with hyphen preservation
- **Addresses**: Standardized formatting

#### 5. Security and performance
- **RLS enabled** on all dynamic tables
- **Optimized indexes**: user_id, status, coordinates (GIN)
- **User policies**: SELECT, INSERT, UPDATE, DELETE

### Benefits achieved
- ✅ **Scalability**: Unlimited support for new countries
- ✅ **Performance**: Segmented and indexed data
- ✅ **Flexibility**: Adaptable schemas per country
- ✅ **Maintenance**: Automatic validation according to local standards

### Points of vigilance
- Future migration of existing data required
- Monitoring of automatic table creation
- Thorough testing required for each new country

### Suggested next steps
1. Comprehensive testing with FR and US data
2. Migration of existing data from `property_demands`
3. Addition of new countries (CA, DE, etc.)
4. Cross-country query optimization if necessary

---

## Documentation conventions

### Note format
- **Date**: YYYY-MM-DD
- **Title**: Concise improvement description
- **Structure**: Problem → Solution → Benefits → Vigilance → Next steps

### Maintenance
- Daily updates of improvements
- Major change versioning
- Technical decision history preservation
