## 11-04-2013

### Get the proto files

* Install `protobuf-2.5.0.tar.gz` for python (downloaded from https://code.google.com/p/protobuf/downloads/list)

		python setup.py install
		
* Download `protobuf-re-tools.zip` from http://www.sysdream.com/reverse-engineering-protobuf-apps
* Run it against Pages:

		python protobuf-re-tools/protod/protod.py /Applications/Pages.app/Contents/MacOS/Pages
		
* The resulting files are `.proto` files, stored in `proto files`:

		TPArchives.proto
		TPCommandArchives.proto
		TSCEArchives.proto
		TSCH3DArchives.proto
		TSCHArchives.Common.proto
		TSDArchives.proto
		TSDCommandArchives.proto
		TSPArchiveMessages.proto
		TSPDatabaseMessages.proto
		TSTArchives.proto
		TSTCommandArchives.proto
		TSWPArchives.proto
		TSWPCommandArchives.proto

### Read a pages document

* Pages document are file packages with the following contents

		Data                    -->   (empty directory in simple documents?)
		Index.zip
		Metadata                -->   directory with various plists
		preview-micro.jpg
		preview-web.jpg
		preview.jpg

* The file `Index.zip` is a zip file with various `iwa` files:

		AnnotationAuthorStorage.iwa
		CalculationEngine.iwa
		Document.iwa
		DocumentStylesheet.iwa
		Metadata.iwa
		Tables --> directory with more iwa files
		ThemeStylesheet.iwa
		ViewState.iwa

* The `iwa` files can be read using the protobuf formats

