# CH22_NSPredicate_ObjectiveCNotesForPros
CH22_NSPredicate_ObjectiveCNotesForPros

``` objective-c
//
//  main.m
//  NSPredicate
//
//  Created by Carlos Santiago Cruz on 5/11/19.
//  Copyright © 2019 Carlos Santiago Cruz. All rights reserved.
//

#import <Foundation/Foundation.h>

int main(int argc, const char * argv[]) {
    @autoreleasepool {
        NSArray *array = @[
                           @{
                               @"id": @"7CDF6D22-8D36-49C2-84FE-E31EECCECB71",
                               @"title": @"Jackie Chan Strike Movie",
                               @"url": @"http://abc.com/playback.m3u8",
                               @"thumbnailURL": @"http://abc.com/thumbnail.png",
                               @"isMovie" : @1
                               },
                           @{
                               @"id": @"7CDF6D22-8D36-49C2-84FE-E31EECCECB72",
                               @"title": @"Sherlock homes",
                               @"url": @"http://abc.com/playback.m3u8",
                               @"thumbnailURL": @"http://abc.com/thumbnail.png",
                               @"isMovie" : @0
                               },
                           @{
                               @"id": @"7CDF6D22-8D36-49C2-84FE-E31EECCECB73",
                               @"title": @"Titanic",
                               @"url": @"http://abc.com/playback.m3u8",
                               @"thumbnailURL": @"http://abc.com/thumbnail.png",
                               @"isMovie" : @1
                               },
                           @{
                               @"id": @"7CDF6D22-8D36-49C2-84FE-E31EECCECB74",
                               @"title": @"Star Wars",
                               @"url": @"http://abc.com/playback.m3u8",
                               @"thumbnailURL": @"http://abc.com/thumbnail.png",
                               @"isMovie" : @1
                           },
                           @{
                               @"id": @"7CDF6D22-8D36-49C2-84FE-E31EECCECB75",
                               @"title": @"Pokemon",
                               @"url": @"http://abc.com/playback.m3u8",
                               @"thumbnailURL": @"http://abc.com/thumbnail.png",
                               @"isMovie" : @0
                               },
                           @{
                               @"id": @"7CDF6D22-8D36-49C2-84FE-E31EECCECB76",
                               @"title": @"Avatar",
                               @"url": @"http://abc.com/playback.m3u8",
                               @"thumbnailURL": @"http://abc.com/thumbnail.png",
                               @"isMovie" : @1
                               },
                           @{
                               @"id": @"7CDF6D22-8D36-49C2-84FE-E31EECCECB77",
                               @"title": @"Popey",
                               @"url": @"http://abc.com/playback.m3u8",
                               @"thumbnailURL": @"http://abc.com/thumbnail.png",
                               @"isMovie" : @1
                               },
                           @{
                               @"id": @"7CDF6D22-8D36-49C2-84FE-E31EECCECB78",
                               @"title": @"Tom and Jerry",
                               @"url": @"http://abc.com/playback.m3u8",
                               @"thumbnailURL": @"http://abc.com/thumbnail.png",
                               @"isMovie" : @1
                               },
                           @{
                               @"id": @"7CDF6D22-8D36-49C2-84FE-E31EECCECB79",
                               @"title": @"The wolf",
                               @"url": @"http://abc.com/playback.m3u8",
                               @"thumbnailURL": @"http://abc.com/thumbnail.png",
                               @"isMovie" : @1
                               }
                           
                           ];
        // *** Case Insensitive comparison with exact title match ***
        NSPredicate *filterByNameCIS = [NSPredicate predicateWithFormat:@"self.title LIKE[cd] %@",@"Tom and Jerry"];
        NSLog(@"Filter By Name(CIS) : %@",[array filteredArrayUsingPredicate:filterByNameCIS]);
        
        // *** Find movies except given ids ***
        NSPredicate *filterByNotInIds = [NSPredicate predicateWithFormat:@"NOT (self.id IN %@)",@[@"7CDF6D22-8D36-49C2-84FE-E31EECCECB79", @"7CDF6D22-8D36-49C2-84FE-E31EECCECB76"]]; NSLog(@"Filte r movies except given Ids : %@",[array filteredArrayUsingPredicate:filterByNotInIds]);
        
        //*** Find all the objects which is of type movie, Both the syntax are valid ***
         NSPredicate *filterByMovieType = [NSPredicate predicateWithFormat:@"self.isMovie = %@",@1];
         // OR
         //NSPredicate *filterByMovieType = [NSPredicate predicateWithFormat:@"self.isMovie = %@",[NSNumber numberWithBool:YES]];
         NSLog(@"Filter By Movie Type : %@",[array filteredArrayUsingPredicate:filterByMovieType]);
    }
    return 0;
}
```



