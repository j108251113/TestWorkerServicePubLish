# TestWorkerServicePubLish

~~Visual Studio 的發佈功能不知道為何讀取不到 `.pubxml` 內 `PropertyGroup` 以外的內容~~

預期的行為是發佈後的發佈資料夾內不會有 `appsettings.Development.json`

測試後發現必須明確指定 `PublishProfile` 的路徑才能讓 `.pubxml` 內的設定生效

要實現不把 `appsettings.Development.json` 也複製過去，設定也必須這樣寫才會生效
```xml
  <ItemGroup>
	  <Content Update="appsettings.Development.json" CopyToPublishDirectory="Never"></Content>
  </ItemGroup>
```

如果使用以下寫法會沒有作用，但在 .net core web 專案是會生效的
```
	<ItemGroup>
		<Content Update="appsettings.Development.json">
			<CopyToPublishDirectory>Never</CopyToPublishDirectory>
			<CopyToOutputDirectory>Never</CopyToOutputDirectory>
		</Content>
	</ItemGroup>
```