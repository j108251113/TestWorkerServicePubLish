# TestWorkerServicePubLish

~~Visual Studio ���o�G�\�ण���D����Ū������ `.pubxml` �� `PropertyGroup` �H�~�����e~~

�w�����欰�O�o�G�᪺�o�G��Ƨ������|�� `appsettings.Development.json`

���ի�o�{�������T���w `PublishProfile` �����|�~���� `.pubxml` �����]�w�ͮ�

�n��{���� `appsettings.Development.json` �]�ƻs�L�h�A�]�w�]�����o�˼g�~�|�ͮ�
```xml
  <ItemGroup>
	  <Content Update="appsettings.Development.json" CopyToPublishDirectory="Never"></Content>
  </ItemGroup>
```

�p�G�ϥΥH�U�g�k�|�S���@�ΡA���b .net core web �M�׬O�|�ͮĪ�
```
	<ItemGroup>
		<Content Update="appsettings.Development.json">
			<CopyToPublishDirectory>Never</CopyToPublishDirectory>
			<CopyToOutputDirectory>Never</CopyToOutputDirectory>
		</Content>
	</ItemGroup>
```