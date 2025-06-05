
# Infrastructure & Database Improvements

Documentation of database architecture, performance optimizations, and technical infrastructure enhancements.

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

## Database Architecture Principles

### Table Design Standards
- **Dynamic Creation**: Tables created on-demand based on business needs
- **Country Segmentation**: Separate tables per country for performance and compliance
- **Normalized Structures**: Data validation according to local standards
- **Optimized Indexing**: Strategic indexes for common query patterns

### Performance Optimization
- **Query Segmentation**: Country-specific queries avoid full table scans
- **Index Strategy**: Composite indexes for user_id, status, and geographic data
- **RLS Implementation**: Row-level security for data isolation
- **Connection Pooling**: Efficient database connection management

### Security Framework
- **Row-Level Security (RLS)**: Enabled on all user data tables
- **User Policies**: Granular permissions for SELECT, INSERT, UPDATE, DELETE
- **Data Encryption**: Sensitive data encrypted at rest and in transit
- **Audit Logging**: Comprehensive logging of data access and modifications

### Scalability Considerations
- **Horizontal Partitioning**: Country-based table separation
- **Vertical Scaling**: Optimized queries and indexing strategies
- **Caching Layers**: Strategic caching for frequently accessed data
- **Load Balancing**: Database load distribution for high availability

---

*Infrastructure priorities: Data migration tooling, cross-country analytics, performance monitoring, backup strategies.*
