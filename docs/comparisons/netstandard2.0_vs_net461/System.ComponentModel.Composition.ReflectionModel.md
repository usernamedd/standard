# System.ComponentModel.Composition.ReflectionModel

``` diff
+namespace System.ComponentModel.Composition.ReflectionModel {
+    [System.Runtime.InteropServices.StructLayoutAttribute(System.Runtime.InteropServices.LayoutKind.Sequential)]
+    public struct LazyMemberInfo {
+        public LazyMemberInfo(MemberInfo member);
+        public LazyMemberInfo(MemberTypes memberType, Func<MemberInfo[]> accessorsCreator);
+        public LazyMemberInfo(MemberTypes memberType, params MemberInfo[] accessors);
+        public MemberTypes MemberType { get; }
+        public override bool Equals(object obj);
+        public MemberInfo[] GetAccessors();
+        public override int GetHashCode();
+        public static bool operator ==(LazyMemberInfo left, LazyMemberInfo right);
+        public static bool operator !=(LazyMemberInfo left, LazyMemberInfo right);
+    }
+    public static class ReflectionModelServices {
+        public static ExportDefinition CreateExportDefinition(LazyMemberInfo exportingMember, string contractName, Lazy<IDictionary<string, object>> metadata, ICompositionElement origin);
+        public static ContractBasedImportDefinition CreateImportDefinition(LazyMemberInfo importingMember, string contractName, string requiredTypeIdentity, IEnumerable<KeyValuePair<string, Type>> requiredMetadata, ImportCardinality cardinality, bool isRecomposable, bool isPreRequisite, CreationPolicy requiredCreationPolicy, IDictionary<string, object> metadata, bool isExportFactory, ICompositionElement origin);
+        public static ContractBasedImportDefinition CreateImportDefinition(LazyMemberInfo importingMember, string contractName, string requiredTypeIdentity, IEnumerable<KeyValuePair<string, Type>> requiredMetadata, ImportCardinality cardinality, bool isRecomposable, CreationPolicy requiredCreationPolicy, IDictionary<string, object> metadata, bool isExportFactory, ICompositionElement origin);
+        public static ContractBasedImportDefinition CreateImportDefinition(LazyMemberInfo importingMember, string contractName, string requiredTypeIdentity, IEnumerable<KeyValuePair<string, Type>> requiredMetadata, ImportCardinality cardinality, bool isRecomposable, CreationPolicy requiredCreationPolicy, ICompositionElement origin);
+        public static ContractBasedImportDefinition CreateImportDefinition(Lazy<ParameterInfo> parameter, string contractName, string requiredTypeIdentity, IEnumerable<KeyValuePair<string, Type>> requiredMetadata, ImportCardinality cardinality, CreationPolicy requiredCreationPolicy, IDictionary<string, object> metadata, bool isExportFactory, ICompositionElement origin);
+        public static ContractBasedImportDefinition CreateImportDefinition(Lazy<ParameterInfo> parameter, string contractName, string requiredTypeIdentity, IEnumerable<KeyValuePair<string, Type>> requiredMetadata, ImportCardinality cardinality, CreationPolicy requiredCreationPolicy, ICompositionElement origin);
+        public static ComposablePartDefinition CreatePartDefinition(Lazy<Type> partType, bool isDisposalRequired, Lazy<IEnumerable<ImportDefinition>> imports, Lazy<IEnumerable<ExportDefinition>> exports, Lazy<IDictionary<string, object>> metadata, ICompositionElement origin);
+        public static ContractBasedImportDefinition GetExportFactoryProductImportDefinition(ImportDefinition importDefinition);
+        public static LazyMemberInfo GetExportingMember(ExportDefinition exportDefinition);
+        public static LazyMemberInfo GetImportingMember(ImportDefinition importDefinition);
+        public static Lazy<ParameterInfo> GetImportingParameter(ImportDefinition importDefinition);
+        public static Lazy<Type> GetPartType(ComposablePartDefinition partDefinition);
+        public static bool IsDisposalRequired(ComposablePartDefinition partDefinition);
+        public static bool IsExportFactoryImportDefinition(ImportDefinition importDefinition);
+        public static bool IsImportingParameter(ImportDefinition importDefinition);
+        public static bool TryMakeGenericPartDefinition(ComposablePartDefinition partDefinition, IEnumerable<Type> genericParameters, out ComposablePartDefinition specialization);
+    }
+}
```

