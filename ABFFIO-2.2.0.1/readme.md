Contents of `ABF_FileSupportPack.zip` which is distributed with pClamp 11.2 (downloadable from Molecular Devices website)

### ABFFILES.H

```c
bool ABF_BuildErrorText(int nErrorNum, const char *szFileName, char *sTxtBuf, UINT uMaxLen);
bool ABF_CalculateCRC(int nFile, int *pnError);
bool ABF_Close(int nFile, int *pnError);
bool ABF_EpisodeFromSynchCount(int nFile, const ABFFileHeader *pFH, dword *pdwSynchCount, dword *pdwEpisode, int *pnError);
bool ABF_FormatDelta(const ABFFileHeader *pFH, const ABFDelta *pDelta, char *pszText, UINT uTextLen, int *pnError);
bool ABF_FormatTag(int nFile, const ABFFileHeader *pFH, long lTagNumber, char *pszBuffer, UINT uSize, int *pnError);
bool ABF_GetEpisodeDuration(int nFile, const ABFFileHeader *pFH, dword dwEpisode, double *pdDuration, int *pnError);
bool ABF_GetEpisodeFileOffset(int nFile, const ABFFileHeader *pFH, dword dwEpisode, dword *pdwFileOffset, int *pnError);
bool ABF_GetFileHandle(int nFile, HANDLE *phHandle, int *pnError);
bool ABF_GetFileName(int nFile, LPSTR pszFilename, UINT uTextLen, int *pnError );
bool ABF_GetMissingSynchCount(int nFile, const ABFFileHeader *pFH, dword dwEpisode, dword *pdwMissingSynchCount, int *pnError);
bool ABF_GetNumSamples(int nFile, const ABFFileHeader *pFH, dword dwEpisode, UINT *puNumSamples, int *pnError);
bool ABF_GetStartTime(int nFile, const ABFFileHeader *pFH, int nChannel, dword dwEpisode, double *pdStartTime, int *pnError);
bool ABF_GetTrialDuration(int nFile, const ABFFileHeader *pFH, double *pdDuration, int *pnError);
bool ABF_GetVoiceTag(int nFile, const ABFFileHeader *pFH, UINT uTag, LPCSTR pszFileName, long lDataOffset, ABFVoiceTagInfo *pVTI, int *pnError);
bool ABF_GetWaveform(int nFile, const ABFFileHeader *pFH, UINT uDACChannel, dword dwEpisode, float *pfBuffer, int *pnError);
bool ABF_HasData(int nFile, const ABFFileHeader *pFH);
bool ABF_HasOverlappedData(int nFile, bool *pbHasOverlapped, int *pnError);
bool ABF_IsABFFile(const char *szFileName, int *pnDataFormat, int *pnError);
bool ABF_MultiplexRead(int nFile, const ABFFileHeader *pFH, dword dwEpisode, void *pvBuffer, UINT *puSizeInSamples, int *pnError);
bool ABF_MultiplexWrite(int nFile, const ABFFileHeader *pFH, UINT uFlags, const void *pvBuffer, dword dwEpiStart, UINT uSizeInSamples, int *pnError);
bool ABF_ParamReader(int nFile, ABFFileHeader *pFH, int *pnError);
bool ABF_ParamWriter(const char *pszFilename, ABFFileHeader *pFH, int *pnError);
bool ABF_ParseStringAnnotation(LPCSTR pszAnn, LPSTR pszName, UINT uSizeName, LPSTR pszValue, UINT uSizeValue, int *pnError);
bool ABF_PlayVoiceTag(int nFile, const ABFFileHeader *pFH, UINT uTag, int *pnError);
bool ABF_ReadAnnotation(int nFile, const ABFFileHeader *pFH, dword dwIndex, LPSTR pszText, dword dwBufSize, int *pnError );
bool ABF_ReadChannel(int nFile, const ABFFileHeader *pFH, int nChannel, dword dwEpisode, float *pfBuffer, UINT *puNumSamples, int *pnError);
bool ABF_ReadDACFileEpi(int nFile, const ABFFileHeader *pFH, short *pnDACArray, UINT nChannel, dword dwEpisode, int *pnError);
bool ABF_ReadDeltas(int nFile, const ABFFileHeader *pFH, dword dwFirstDelta, ABFDelta *pDeltaArray, UINT uNumDeltas, int *pnError);
bool ABF_ReadIntegerAnnotation(int nFile, const ABFFileHeader *pFH, dword dwIndex, LPSTR pszName, UINT uSizeName, int *pnValue, int *pnError );
bool ABF_ReadOpen(LPCSTR szFileName, int *phFile, UINT fFlags, ABFFileHeader *pFH, UINT *puMaxSamples, dword *pdwMaxEpi, int *pnError );
bool ABF_ReadRawChannel(int nFile, const ABFFileHeader *pFH, int nChannel, dword dwEpisode, void *pvBuffer, UINT *puNumSamples, int *pnError);
bool ABF_ReadScopeConfig(int nFile, ABFFileHeader *pFH, ABFScopeConfig *pCfg, UINT uMaxScopes, int *pnError);
bool ABF_ReadStatisticsConfig(int nFile, const ABFFileHeader *pFH, ABFScopeConfig *pCfg, int *pnError);
bool ABF_ReadStringAnnotation(int nFile, const ABFFileHeader *pFH, dword dwIndex, LPSTR pszName, UINT uSizeName, LPSTR pszValue, UINT uSizeValue, int *pnError );
bool ABF_ReadTags(int nFile, const ABFFileHeader *pFH, dword dwFirstTag, ABFTag *pTagArray, UINT uNumTags, int *pnError);
bool ABF_SaveVoiceTag(int nFile, LPCSTR pszFileName, long lDataOffset, ABFVoiceTagInfo *pVTI, int *pnError);
bool ABF_SetChunkSize(int hFile, ABFFileHeader *pFH, UINT *puMaxSamples, dword *pdwMaxEpi, int *pnError );
bool ABF_SetEpisodeStart(int nFile, UINT uEpisode, UINT uEpiStart, int *pnError);
bool ABF_SetErrorCallback(int nFile, ABFCallback fnCallback, void *pvThisPointer, int *pnError);
bool ABF_SetOverlap(int nFile, const ABFFileHeader *pFH, bool bAllowOverlap, int *pnError);
bool ABF_SynchCountFromEpisode(int nFile, const ABFFileHeader *pFH, dword dwEpisode, dword *pdwSynchCount, int *pnError);
bool ABF_UpdateEpisodeSamples(int nFile, const ABFFileHeader *pFH, int nChannel, UINT uEpisode, UINT uStartSample, UINT uNumSamples, float *pfBuffer, int *pnError);
bool ABF_UpdateHeader(int nFile, ABFFileHeader *pFH, int *pnError);
bool ABF_UpdateTag(int nFile, UINT uTag, const ABFTag *pTag, int *pnError);
bool ABF_WriteAnnotation(int nFile, ABFFileHeader *pFH, LPCSTR pszText, int *pnError );
bool ABF_WriteDACFileEpi(int nFile, ABFFileHeader *pFH, UINT uDACChannel, const short *pnDACArray, int *pnError);
bool ABF_WriteDelta(int nFile, ABFFileHeader *pFH, const ABFDelta *pDelta, int *pnError);
bool ABF_WriteIntegerAnnotation(int nFile, ABFFileHeader *pFH, LPCSTR pszName, int nData, int *pnError );
bool ABF_WriteOpen(LPCSTR szFileName, int *phFile, UINT fFlags, ABFFileHeader *pFH, int *pnError );
bool ABF_WriteRawData(int nFile, const void *pvBuffer, dword dwSizeInBytes, int *pnError);
bool ABF_WriteScopeConfig(int nFile, ABFFileHeader *pFH, int nScopes, /*const*/ ABFScopeConfig *pCfg, int *pnError);
bool ABF_WriteStatisticsConfig(int nFile, ABFFileHeader *pFH, const ABFScopeConfig *pCfg, int *pnError);
bool ABF_WriteStringAnnotation(int nFile, ABFFileHeader *pFH, LPCSTR pszName, LPCSTR pszData, int *pnError );
bool ABF_WriteTag(int nFile, ABFFileHeader *pFH, const ABFTag *pTag, int *pnError);
dword ABF_GetMaxAnnotationSize(int nFile, const ABFFileHeader *pFH );
uint ABF_GetActualEpisodes(int nFile);
uint ABF_GetActualSamples(int nFile);
void ABF_Cleanup(void);
```
