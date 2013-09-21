BigXlsxBundle
=============

Symfony2 Bundle for generating large multi-sheeted xlsx files with low memory usage.

This Bundle basically acts as a replacement for offering csv files with large datasets to download. This because the CSV format can be troublesome when it comes to difference in default cell separators en line-endings on specific operating systems.

Also, CSV cannot handle multiple sheets.

This bundle uses the 'codeplex/phpexcel' bundle but tries to get rid of the enormous execution time and memory consumption when one wants to handle large datasets in a xlsx.


Usage
-----

		/** @var $service BigXlsxService */
		$service = $container->get('bassim_big_xlsx.service');
		$service->create();

		$data = array();
		for ($i=0;$i<1;$i++) {
			$data[] = array($i, "name_".$i);
		}

		$service->addSheet(0, "test Sheet_0", array("id","name"), $data);
		$file = $service->get();

  
