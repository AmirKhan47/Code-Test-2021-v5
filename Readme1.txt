1) app/Http/Controllers/BookingController.php

1-> in this public function index(Request $request) should be using proper laravel authorization https://laravel.com/docs/9.x/authorization techniques by writing gates and policies.

2-> this controller is pretty much ok distanceFeed() this function should be handled seperatly the function should be small and simple use different helper to make it look good and readable.

2) app/Repository/BookingRepository.php

1-> this is realy messed up BookingRepository it has too much code it needs alot fo refactoring too much lines of code things needs to be seperated like convertToHoursMins($time, $format = '%02dh %02dmin') we can put this function into helpers.php, soo much ifelse are used and no comment someone has to go through complete code plus there is no code formating, there has to be some description about whats the working of functions

2-> using too much queries with DB facade we can use one time and use filter on the data?

3-> why using facades though why not go with query builder also there are alot of comments in the code

4-> again changeWithdrawafter24Status($job, $data) why not use helper there is soo much stuff that needs to be seperated