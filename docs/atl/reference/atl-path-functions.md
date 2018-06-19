---
title: ATL 경로 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- ATL, path
f1_keywords:
- ATLPATH/ATL::ATLPath::AddBackslash
- ATLPATH/ATL::ATLPath::AddExtension
- ATLPATH/ATL::ATLPath::Append
- ATLPATH/ATL::ATLPath::BuildRoot
- ATLPATH/ATL::ATLPath::Canonicalize
- ATLPATH/ATL::ATLPath::Combine
- ATLPATH/ATL::ATLPath::CommonPrefix
- ATLPATH/ATL::ATLPath::CompactPath
- ATLPATH/ATL::ATLPath::CompactPathEx
- ATLPATH/ATL::ATLPath::FileExists
- ATLPATH/ATL::ATLPath::FindExtension
- ATLPATH/ATL::ATLPath::FindFileName
- ATLPATH/ATL::ATLPath::GetDriveNumber
- ATLPATH/ATL::ATLPath::IsDirectory
- ATLPATH/ATL::ATLPath::IsFileSpec
- ATLPATH/ATL::ATLPath::IsPrefix
- ATLPATH/ATL::ATLPath::IsRelative
- ATLPATH/ATL::ATLPath::IsRoot
- ATLPATH/ATL::ATLPath::IsSameRoot
- ATLPATH/ATL::ATLPath::IsUNC
- ATLPATH/ATL::ATLPath::IsUNCServer
- ATLPATH/ATL::ATLPath::IsUNCServerShare
- ATLPATH/ATL::ATLPath::MakePretty
- ATLPATH/ATL::ATLPath::MatchSpec
- ATLPATH/ATL::ATLPath::QuoteSpaces
- ATLPATH/ATL::ATLPath::RelativePathTo
- ATLPATH/ATL::ATLPath::RemoveArgs
- ATLPATH/ATL::ATLPath::RemoveBackslash
- ATLPATH/ATL::ATLPath::RemoveBlanks
- ATLPATH/ATL::ATLPath::RemoveExtension
- ATLPATH/ATL::ATLPath::RemoveFileSpec
- ATLPATH/ATL::ATLPath::RenameExtension
- ATLPATH/ATL::ATLPath::SkipRoot
- ATLPATH/ATL::ATLPath::StripPath
- ATLPATH/ATL::ATLPath::StripToRoot
- ATLPATH/ATL::ATLPath::UnquoteSpaces
ms.assetid: d1ec2b8d-7ec7-43ea-90dd-0a740d2a742b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38286d169591dd55f7a2618332b6f5d5c9c86719
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366538"
---
# <a name="atl-path-functions"></a>ATL 경로 함수

형식의 경로 조작 하기 위한 ATLPath 클래스를 제공 하는 ATL [CPathT](cpatht-class.md)합니다. 이 코드는 atlpath.h에서 찾을 수 있습니다.  
  
### <a name="related-classes"></a>관련된 클래스  
  
|||  
|-|-|  
|[CPathT 클래스](cpatht-class.md)|이 클래스는 경로 나타냅니다.|  

### <a name="related-typedefs"></a>관련된 Typedefs  
  
|||  
|-|-|  
|`CPath`|특수화 [CPathT](cpatht-class.md) 를 사용 하 여 `CString`합니다.|  
|`CPathA`|특수화 [CPathT](cpatht-class.md) 를 사용 하 여 `CStringA`합니다.|  
|`CPathW`|특수화 [CPathT](cpatht-class.md) 를 사용 하 여 `CStringW`합니다.|  
  
### <a name="functions"></a>함수  
  
|||  
|-|-|  
|[ATLPath::AddBackslash](#addbackslash)|이 함수는 오버 로드 된 래퍼입니다 [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561)합니다.|  
|[ATLPath::AddExtension](#addextension)|이 함수는 오버 로드 된 래퍼입니다 [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563)합니다.|  
|[ATLPath::Append](#append)|이 함수는 오버 로드 된 래퍼입니다 [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565)합니다.|  
|[ATLPath::BuildRoot](#buildroot)|이 함수는 오버 로드 된 래퍼입니다 [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567)합니다.|  
|[ATLPath::Canonicalize](#canonicalize)|이 함수는 오버 로드 된 래퍼입니다 [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569)합니다.|  
|[ATLPath::Combine](#combine)|이 함수는 오버 로드 된 래퍼입니다 [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571)합니다.|  
|[ATLPath::CommonPrefix](#commonprefix)|이 함수는 오버 로드 된 래퍼입니다 [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574)합니다.|  
|[ATLPath::CompactPath](#compactpath)|이 함수는 오버 로드 된 래퍼입니다 [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575)합니다.|  
|[ATLPath::CompactPathEx](#compactpathex)|이 함수는 오버 로드 된 래퍼입니다 [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578)합니다.|  
|[ATLPath::FileExists](#fileexists)|이 함수는 오버 로드 된 래퍼입니다 [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584)합니다.|  
|[ATLPath::FindExtension](#findextension)|이 함수는 오버 로드 된 래퍼입니다 [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587)합니다.|  
|[ATLPath::FindFileName](#findfilename)|이 함수는 오버 로드 된 래퍼입니다 [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589)합니다.|  
|[ATLPath::GetDriveNumber](#getdrivenumber)|이 함수는 오버 로드 된 래퍼입니다 [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612)합니다.|  
|[ATLPath::IsDirectory](#isdirectory)|이 함수는 오버 로드 된 래퍼입니다 [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621)합니다.|  
|[ATLPath::IsFileSpec](#isfilespec)|이 함수는 오버 로드 된 래퍼입니다 [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627)합니다.|  
|[ATLPath::IsPrefix](#isprefix)|이 함수는 오버 로드 된 래퍼입니다 [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650)합니다.|  
|[ATLPath::IsRelative](#isrelative)|이 함수는 오버 로드 된 래퍼입니다 [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660)합니다.|  
|[ATLPath::IsRoot](#isroot)|이 함수는 오버 로드 된 래퍼입니다 [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674)합니다.|  
|[ATLPath::IsSameRoot](#issameroot)|이 함수는 오버 로드 된 래퍼입니다 [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687)합니다.|  
|[ATLPath::IsUNC](#isunc)|이 함수는 오버 로드 된 래퍼입니다 [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712)합니다.|  
|[ATLPath::IsUNCServer](#isuncserver)|이 함수는 오버 로드 된 래퍼입니다 [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722)합니다.|  
|[ATLPath::IsUNCServerShare](#isuncservershare)|이 함수는 오버 로드 된 래퍼입니다 [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723)합니다.|  
|[ATLPath::MakePretty](#makepretty)|이 함수는 오버 로드 된 래퍼입니다 [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725)합니다.|  
|[ATLPath::MatchSpec](#matchspec)|이 함수는 오버 로드 된 래퍼입니다 [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727)합니다.|  
|[ATLPath::QuoteSpaces](#quotespaces)|이 함수는 오버 로드 된 래퍼입니다 [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739)합니다.|  
|[ATLPath::RelativePathTo](#relativepathto)|이 함수는 오버 로드 된 래퍼입니다 [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740)합니다.|  
|[ATLPath::RemoveArgs](#removeargs)|이 함수는 오버 로드 된 래퍼입니다 [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742)합니다.|  
|[ATLPath::RemoveBackslash](#removebackslash)|이 함수는 오버 로드 된 래퍼입니다 [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743)합니다.|  
|[ATLPath::RemoveBlanks](#removeblanks)|이 함수는 오버 로드 된 래퍼입니다 [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745)합니다.|  
|[ATLPath::RemoveExtension](#removeextension)|이 함수는 오버 로드 된 래퍼입니다 [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746)합니다.|  
|[ATLPath::RemoveFileSpec](#removefilespec)|이 함수는 오버 로드 된 래퍼입니다 [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748)합니다.|  
|[ATLPath::RenameExtension](#renameextension)|이 함수는 오버 로드 된 래퍼입니다 [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749)합니다.|  
|[ATLPath::SkipRoot](#skiproot)|이 함수는 오버 로드 된 래퍼입니다 [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754)합니다.|  
|[ATLPath::StripPath](#strippath)|이 함수는 오버 로드 된 래퍼입니다 [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756)합니다.|  
|[ATLPath::StripToRoot](#striptoroot)|이 함수는 오버 로드 된 래퍼입니다 [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757)합니다.|  
|[ATLPath::UnquoteSpaces](#unquotespaces)|이 함수는 오버 로드 된 래퍼입니다 [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763)합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlpath.h  

## <a name="addbackslash"></a> ATLPath::AddBackSlash

이 함수는 오버 로드 된 래퍼입니다 [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline char* AddBackslash(char* pszPath);  
inline wchar_t* AddBackslash(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="addextension"></a> ATLPath::AddExtension
 이 함수는 오버 로드 된 래퍼입니다 [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL AddExtension(char* pszPath, const char* pszExtension);  
inline BOOL AddExtension(wchar_t* pszPath, const wchar_t* pszExtension);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563) 대 한 자세한 내용은 합니다. 
  
## <a name="append"></a> ATLPath::Append
 이 함수는 오버 로드 된 래퍼입니다 [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL Append(char* pszPath, const char* pszMore);  
inline BOOL Append(wchar_t* pszPath, const wchar_t* pszMore);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="buildroot"></a> ATLPath::BuildRoot
 이 함수는 오버 로드 된 래퍼입니다 [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline char* BuildRoot(char* pszPath, int iDrive);  
inline wchar_t* BuildRoot(wchar_t* pszPath, int iDrive);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="canonicalize"></a> ATLPath::Canonicalize
 이 함수는 오버 로드 된 래퍼입니다 [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL Canonicalize(char* pszDest, const char* pszSrc);  
inline BOOL Canonicalize(wchar_t* pszDest, const wchar_t* pszSrc);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="combine"></a> ATLPath::Combine 
이 함수는 오버 로드 된 래퍼입니다 [PathCombine](https://msdn.microsoft.com/en-us/library/windows/desktop/bb773571)합니다.  

### <a name="syntax"></a>구문  
```
inline char* Combine(  
   char* pszDest,
   const char* pszDir,
   const char* pszFile 
);

inline wchar_t* Combine(  
   wchar_t* pszDest,
   const wchar_t* pszDir,
   const wchar_t* pszFile);
```
### <a name="remarks"></a>설명
자세한 내용은 PathCombine를 참조 하십시오.


## <a name="commonprefix"></a> ATLPath::CommonPrefix
 이 함수는 오버 로드 된 래퍼입니다 [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline int CommonPrefix(  
   const char* pszFile1, 
   const char* pszFile2,  
   char* pszDest);  

inline int CommonPrefix(  
   const wchar_t* pszFile1,  
   const wchar_t* pszFile2,  
   wchar_t* pszDest);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="compactpath"></a> ATLPath::CompactPath
 이 함수는 오버 로드 된 래퍼입니다 [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL CompactPath(  
   HDC hDC,  
   char* pszPath,  
   UINT dx);  

inline BOOL CompactPath(  
   HDC hDC,  
   wchar_t* pszPath,  
   UINT dx);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="compactpathex"></a> ATLPath::CompactPathEx
 이 함수는 오버 로드 된 래퍼입니다 [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL CompactPathEx(  
   char* pszDest,  
   const char* pszSrc,  
   UINT nMaxChars,  
   DWORD dwFlags);  

inline BOOL CompactPathEx(  
   wchar_t* pszDest,  
   const wchar_t* pszSrc,  
   UINT nMaxChars,  
   DWORD dwFlags);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="fileexists"></a> ATLPath::FileExists
 이 함수는 오버 로드 된 래퍼입니다 [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL FileExists(const char* pszPath);  
inline BOOL FileExists(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="findextension"></a> ATLPath::FindExtension
 이 함수는 오버 로드 된 래퍼입니다 [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline char* FindExtension(const char* pszPath);  
inline wchar_t* FindExtension(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="findfilename"></a> ATLPath::FindFileName
 이 함수는 오버 로드 된 래퍼입니다 [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline char* FindFileName(const char* pszPath);  
inline wchar_t* FindFileName(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="getdrivenumber"></a> ATLPath::GetDriveNumber  
 이 함수는 오버 로드 된 래퍼입니다 [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline int GetDriveNumber(const char* pszPath);  
inline int GetDriveNumber(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612) 대 한 자세한 내용은 합니다.  
  
 


## <a name="isdirectory"></a>  ATLPath::IsDirectory 
이 함수는 오버 로드 된 래퍼입니다 [PathIsDirectory](https://msdn.microsoft.com/en-us/library/windows/desktop/bb773621)합니다.

```  
inline BOOL IsDirectory(const char* pszPath);
inline BOOL IsDirectory(const wchar_t* pszPath);
```  
### <a name="remarks"></a>설명
자세한 내용은 PathIsDirectory를 참조 하십시오.  

## <a name="isfilespec"></a> ATLPath::IsFileSpec
 이 함수는 오버 로드 된 래퍼입니다 [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL IsFileSpec(const char* pszPath);  
inline BOOL IsFileSpec(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="isprefix"></a> ATLPath::IsPrefix
 이 함수는 오버 로드 된 래퍼입니다 [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL IsPrefix(const char* pszPrefix, const char* pszPath);  
inline BOOL IsPrefix(const wchar_t* pszPrefix, const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="isrelative"></a> ATLPath::IsRelative
 이 함수는 오버 로드 된 래퍼입니다 [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL IsRelative(const char* pszPath);  
inline BOOL IsRelative(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="isroot"></a> ATLPath::IsRoot
 이 함수는 오버 로드 된 래퍼입니다 [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL IsRoot(const char* pszPath);  
inline BOOL IsRoot(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="issameroot"></a> ATLPath::IsSameRoot
 이 함수는 오버 로드 된 래퍼입니다 [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL IsSameRoot(const char* pszPath1, const char* pszPath2);  
inline BOOL IsSameRoot(const wchar_t* pszPath1, const wchar_t* pszPath2);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="isunc"></a> ATLPath::IsUNC
 이 함수는 오버 로드 된 래퍼입니다 [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL IsUNC(const char* pszPath);  
inline BOOL IsUNC(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="isuncserver"></a> ATLPath::IsUNCServer
 이 함수는 오버 로드 된 래퍼입니다 [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL IsUNCServer(const char* pszPath);  
inline BOOL IsUNCServer(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="isuncservershare"></a> ATLPath::IsUNCServerShare
 이 함수는 오버 로드 된 래퍼입니다 [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL IsUNCServerShare(const char* pszPath);  
inline BOOL IsUNCServerShare(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="makepretty"></a> ATLPath::MakePretty
 이 함수는 오버 로드 된 래퍼입니다 [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL MakePretty(char* pszPath);  
inline BOOL MakePretty(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="matchspec"></a> ATLPath::MatchSpec  
 이 함수는 오버 로드 된 래퍼입니다 [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL MatchSpec(const char* pszPath, const char* pszSpec);  
inline BOOL MatchSpec(const wchar_t* pszPath, const wchar_t* pszSpec);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="quotespaces"></a> ATLPath::QuoteSpaces  
 이 함수는 오버 로드 된 래퍼입니다 [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline void QuoteSpaces(char* pszPath);  
inline void QuoteSpaces(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="relativepathto"></a> ATLPath::RelativePathTo
 이 함수는 오버 로드 된 래퍼입니다 [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL RelativePathTo(  
   char* pszPath,  
   const char* pszFrom,  
   DWORD dwAttrFrom,  
   const char* pszTo,  
   DWORD dwAttrTo);  

inline BOOL RelativePathTo(  
   wchar_t* pszPath,  
   const wchar_t* pszFrom,  
   DWORD dwAttrFrom,  
   const wchar_t* pszTo,  
   DWORD dwAttrTo);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="removeargs"></a> ATLPath::RemoveArgs  
 이 함수는 오버 로드 된 래퍼입니다 [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline void RemoveArgs(char* pszPath);  
inline void RemoveArgs(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="removebackslash"></a> ATLPath::RemoveBackslash
 이 함수는 오버 로드 된 래퍼입니다 [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline char* RemoveBackslash(char* pszPath);  
inline wchar_t* RemoveBackslash(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="removeblanks"></a> ATLPath::RemoveBlanks
 이 함수는 오버 로드 된 래퍼입니다 [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline void RemoveBlanks(char* pszPath);  
inline void RemoveBlanks(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="removeextension"></a> ATLPath::RemoveExtension
 이 함수는 오버 로드 된 래퍼입니다 [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline void RemoveExtension(char* pszPath);  
inline void RemoveExtension(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="removefilespec"></a> ATLPath::RemoveFileSpec
 이 함수는 오버 로드 된 래퍼입니다 [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL RemoveFileSpec(char* pszPath);  
inline BOOL RemoveFileSpec(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="renameextension"></a> ATLPath::RenameExtension
 이 함수는 오버 로드 된 래퍼입니다 [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL RenameExtension(char* pszPath, const char* pszExt);  
inline BOOL RenameExtension(wchar_t* pszPath, const wchar_t* pszExt);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="skiproot"></a> ATLPath::SkipRoot
 이 함수는 오버 로드 된 래퍼입니다 [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline char* SkipRoot(const char* pszPath);  
inline wchar_t* SkipRoot(const wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="strippath"></a> ATLPath::StripPath
 이 함수는 오버 로드 된 래퍼입니다 [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline void StripPath(char* pszPath);  
inline void StripPath(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756) 대 한 자세한 내용은 합니다.  
  
 
  


## <a name="striptoroot"></a> ATLPath::StripToRoot
 이 함수는 오버 로드 된 래퍼입니다 [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline BOOL StripToRoot(char* pszPath);  
inline BOOL StripToRoot(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757) 대 한 자세한 내용은 합니다.  
  
 
  

## <a name="unquotespaces"></a> ATLPath::UnquoteSpaces
 이 함수는 오버 로드 된 래퍼입니다 [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763)합니다.  
  
### <a name="syntax"></a>구문  
  
```  
inline void UnquoteSpaces(char* pszPath);  
inline void UnquoteSpaces(wchar_t* pszPath);  
```  
  
### <a name="remarks"></a>설명  
 참조 [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763) 대 한 자세한 내용은 합니다.  
  
 
  
 
