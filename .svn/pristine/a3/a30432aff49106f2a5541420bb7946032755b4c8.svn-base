//
//  NSDate+GRG_DateFormatter.m
//  iManager
//
//  Created by administrator on 2018/1/25.
//  Copyright © 2018年 GRGBanking. All rights reserved.
//

#import "NSDate+GRG_DateFormatter.h"
#import "NSDate+Category.h"
#import "NSDateFormatter+Category.h"

@implementation NSDate (GRG_DateFormatter)

+ (NSString *)dateStringWithDaysBeforeNow:(int)count isShowHHmmss:(BOOL)isShowHHmmss {

    NSDate*nowDate = [NSDate date];
    
    NSDate* theDate;
    
    if (count != 0) {
    
        NSTimeInterval  oneDay = 24*60*60*1;  //1天的长度
        theDate = [nowDate initWithTimeIntervalSinceNow: oneDay*count];//initWithTimeIntervalSinceNow是从现在往前后推的秒数
        
        } else {
          
            theDate = nowDate;
            }

    NSDateFormatter *date_formatter = [[NSDateFormatter alloc] init];
    
    isShowHHmmss ? [date_formatter setDateFormat:@"yyyy-MM-dd HH:mm:ss"] : [date_formatter setDateFormat:@"yyyy-MM-dd"];
    
    NSString *the_date_str = [date_formatter stringFromDate:theDate];
    
    return the_date_str;
}

+ (NSString *)dateStringWithDaysBeforeNow:(int)count{
    
    NSDate *date = [NSDate dateWithDaysBeforeNow:count];
    NSDateFormatter *dateFormatter = [NSDateFormatter dateFormatterWithFormat:@"yyyy-MM-dd"];
    NSString *dateStr = [dateFormatter stringFromDate:date];
    
    return dateStr;
}

+ (NSString *)dateStringWithDaysBeforeNow:(int)count isEnd:(BOOL)isEnd{
    NSDate *date = [NSDate dateWithDaysBeforeNow:count];
    NSDateFormatter *dateFormatter = [NSDateFormatter dateFormatterWithFormat:@"yyyy-MM-dd"];
    NSString *dateStr = [dateFormatter stringFromDate:date];
    if (isEnd) {
        return [NSString stringWithFormat:@"%@ 23:59:59",dateStr];
    }else{
        return [NSString stringWithFormat:@"%@ 00:00:00",dateStr];
    }
}

+ (NSArray *)getCurrentYearsMonsDaysHoursMinsSeconds {
    
    NSMutableArray *resArr = [NSMutableArray array];
    NSDate *date = [NSDate date];
    NSDateFormatter *formatter = [[NSDateFormatter alloc] init];
    formatter.dateFormat = @"yyyy-MM-dd HH:mm:ss";
    NSString *currentDateStr = [formatter stringFromDate:date];
    
    NSArray *currentDateArr = [currentDateStr componentsSeparatedByString:@" "];
    NSString *yearsMonsDaysStr = currentDateArr[0];
    NSString *hoursMinsSecondsStr = currentDateArr[1];
    
    NSArray *yearsMonsDaysArr = [yearsMonsDaysStr componentsSeparatedByString:@"-"];
    for (NSString *resStr in yearsMonsDaysArr) {
        
        [resArr addObject:resStr];
    }
    
    NSArray *hoursMinsSecondsArr = [hoursMinsSecondsStr componentsSeparatedByString:@":"];
    for (NSString *resStr in hoursMinsSecondsArr) {
        
        [resArr addObject:resStr];
    }
    
    return [resArr copy];
}

+ (int)compareDate:(NSString*)date01 withDate:(NSString*)date02 dateFormat:(NSString *)dateFormat {
    int ci = 0;
    NSDateFormatter *df = [[NSDateFormatter alloc] init];
    [df setDateFormat:dateFormat];
    NSDate *dt1 = [[NSDate alloc] init];
    NSDate *dt2 = [[NSDate alloc] init];
    dt1 = [df dateFromString:date01];
    dt2 = [df dateFromString:date02];
    NSComparisonResult result = [dt1 compare:dt2];
    switch (result)
    {
            //date01比date02大
        case NSOrderedAscending:
            ci=-1;
            break;
            //date01比date02小
        case NSOrderedDescending:
            ci=1;
            break;
            //date02=date01
            //        case NSOrderedSame: ci=0; break;
        default:
            NSLog(@"erorr dates %@, %@", dt2, dt1);
            break;
    }
    return ci;
}

+ (int)compareNowDateWithDate:(NSString *)date dateFormat:(NSString *)dateFormat {
    
    int ci = 0;
    NSDateFormatter *df = [[NSDateFormatter alloc] init];
    [df setDateFormat:dateFormat];
    NSDate *dt1 = [[NSDate alloc] init];
    dt1 = [df dateFromString:date];
    NSComparisonResult result = [dt1 compare:[NSDate date]];
    switch (result)
    {
            //date01比date02大
        case NSOrderedAscending:
            ci=-1;
            break;
            //date01比date02小
        case NSOrderedDescending:
            ci=1;
            break;
            //date02=date01
            //        case NSOrderedSame: ci=0; break;
        default:
            NSLog(@"erorr dates %@, %@", dt1, [NSDate date]);
            break;
    }
    return ci;
}

@end
