# 0.7.2

### Bug Fixes

* Fixed #113 - Proxies should ignore overriden equals methods
* Fixed #114 - Use specific classloader for loading PropertyMap classes

# 0.7.1

### New Features

* Add support for mapping destination fields using a Converter

### Bug Fixes

* Fixed #111 - Ignore synthetic members and bridge methods

# 0.7.0

### New Features

* Added #92 - Map properties using field references
* Added #102 - Skip properties using field references

### Bug Fixes

* Fixed #47 - Handle explicitly provided convertable properties
* Fixed #79 - Use Objenesis to construct proxies
* Fixed #101 - Handle circular references for boxed primitives
* Fixed #104 - Mapping to existing instances of the same type
* Fixed #106 - Missing null check
* Fixed #109 - Support for mapping primitive wrappers
* Fixed #110 - Problem mapping proxied interfaces to POJOs

### API Changes

For field references:

* Added `PropertyMap.map(Object, Object)`
* Added `PropertyMap.skip(Object)`
* Added `PropertyMap.skip(Object, Object)`

# 0.6.5
4/15/2014

* Fixed #100 - Problem mapping nested collections

# 0.6.4
3/31/2014

* Fixed #95 - Empower ConditionalConverters to handle null properties in source objects
* Fixed #96 - Inherited shaded paths preventing customer converters from running

# 0.6.3 
1/24/2014

* Fixed #80 - ModelMapper extensions use maven backward dependencies
* Fixed #82 - Ignore enums when traversing Enum types
* Fixed #85 - Allow non-void setter return types
* FIxed #91 - Add shaded cglib to Export-Package for better OSGi-support

### API Changes

* For #83 - `MappingContext.create(CS source, CD destination)`

# 0.6.2 
11/5/2013

### New Features

* Added support for mapping Groovy properties
* Improved jOOQ support

### Bug Fixes

* Fixed #74 - Null intermdiate values possible when instance requested via global provider

# 0.6.0 
8/2/2013

### New Features

* Added support for named TypeMaps
* Added support for ValueReaders
* Added 3rd party integration for Jackson, Gson and jOOQ
* Added Simpler mapper EDSL for dealing with providers
* Added #61 - Added UNDERSCORE NameTokenizer
* Added support for explicit mapping of source path strings

### Bug Fixes

* Fixed #8 - Introduced global property conditions
* Fixed #39 - Issue when mapping to a String
* Fixed #49 - Allow implicit mapping to be skipped globally
* Fixed #54 - Fixed OSGI support
* Fixed #56 - Allow full type matching to be required
* Fixed issue with Javabeans name transformers for get/set methods
* Fixed issue with merged TypeMap Providers not being copied

### API Changes

For named TypeMaps:

* Added `ModelMapper.createTypeMap(Class, Class, String)`
* Added `ModelMapper.createTypeMap(Class, Class, String, Configuration)`
* Added `ModelMapper.createTypeMap(Object, Class, String)`
* Added `ModelMapper.createTypeMap(Object, Class, String, Configuration)`
* Added `ModelMapper.map(Object, Class, String)`
* Added `ModelMapper.map(Object, Object, String)`
* Added `ModelMapper.map(Object, Type, String)`

For Value Readers:

* Added `ValueReader` interface to the SPI
* Added `Configuration.getValueReaders()`
* Added `Configuration.addValueReader(ValueReader)`

For mapping source path Strings:

* Added `PropertyMap.source(String)`

Other changes:

* Added `NameTokenizers.UNDERSCORE`
* Changed `Configuration.enableFieldMatching(boolean)` to `setFieldMatchingEnabled(boolean)`
* Changed `Configuration.ignoreAmbiguity(boolean)` to `setAmbiguityIgnored(boolean)`

# 0.5.6 
3/21/2013

### New Features

* Fixed #46 - Property map difficult to construct types
* Added #45 - Android compatibility
* Added #42 - Support for pre and post mapping Converters
* Added #40 - Enhance TypeTokens support

### Bug Fixes

* Fixed #31 - Multiple source properties hierarchy matching problem
* Fixed #38 - Map mocked objects

# 0.5.5 
2/14/2013

### New Features

* Added #34 - Added support for TypeTokens
* Added #23 - Support for combined token matching

### Bug Fixes

* Fixed #32 - Mapping creates instances for null objects
* Fixed #37 - Mappings being incorrectly created

### API Changes

For TypeTokens:

* Added `TypeToken` class
* Added `ModelMapper.map(Object, Type)`


# 0.5.4 
12/22/2012

* Fixed #18 - Updated manifest.mf to contain OSGI bundle information for shaded packages
* Fixed #26 - MM attempts to instantiate primitive wrapper when used in destination Converter
* Fixed #27 - Destinations values are not set in MappingContext
* Fixed #30 - Cannot proxy types without a default constructor

# 0.5.3 
10/22/2012

* Fixed #22 - Destination properties being cached by mutator
* Fixed #21 - Added support for XMLGregorianCalendar conversion
* Fixed issue when merging from a TypeMap with a Converter

# 0.5.2 
10/18/2012

* Fixed #19 - Merged mappings should respect MatchingStrategy
* Fixed #20 - Enum conversion should support String->Enum

# 0.5.1 
9/26/2012

* Fixed scenario where a circular mapping can overrides an existing mapping
* Fixed #11 - Improper shading
* Fixed #10 - Added support for mapped enum conversion

# 0.5.0 
9/12/2012

* Fixed #2 - Add support for circular references
* Fixed #9 - Overriding intemediate objects in provided destinations
* Fixed conversion of char[] to String
* Fixed GC #20 - Improved hashCode in TypeInfoRegistry
* Completed GC #21 - Implement strict matching strategy
* Fixed GC #22 - PropertyMap doesn't work when token matches exist

# 0.4.0 
7/22/2012

* Added support for TypeMap-wide property conditions, converters and providers
* Improved generic type resolution
* Added support for auto-TypeMap merging
* Fixed #3: Disambiguation enhancements
* Fixed #4: Added source to ProvisionRequest
* Fixed #5: Incorrect shading of null paramters
* Fixed #7: Conversion skipped when source is null
* Fixed GC #8: Skipped circular properties
* Fixed GC #10: Incorrect mappings created for multiple source mappings

# 0.3.5 
8/8/2011

* Fixed GC #9: Compatibility with Java 5

# 0.3.4 
7/30/2011

* Simplified the ConditionalConverter SPI
* Fixed GC #4: Exposed conditional converters for mutation via Configuration.getConverters()
* Fixed GC #5: Copy null values for primitives

# 0.3.3 
7/26/2011

* Fixed GC #3: Missing repackaged cglib dependencies
* Fixed GC #2: UnsupportedOperationException when adding ConditionalConverters to configuration

# 0.3.2 
7/19/2011

* Rolled back class file target version to 1.5

# 0.3.1 
6/27/2011

* Added better handling of inherited generic component types
* Added support for shaded properties when using a converter, a skipped mapping or a null source constant

# 0.3.0 
6/20/2011

* Initial public release