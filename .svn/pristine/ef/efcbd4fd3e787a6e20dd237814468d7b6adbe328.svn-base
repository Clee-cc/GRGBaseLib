//
//  NSDate+GRG_DateFormatter.h
//  iManager
//
//  Created by administrator on 2018/1/25.
//  Copyright © 2018年 GRGBanking. All rights reserved.
//

#import <Foundation/Foundation.h>

@interface NSDate (GRG_DateFormatter)

/**
 *  @param  count 同下面count
 *  @param  isShowHHmmss 是否显示时分秒
 *  @desc → 获取count天数前的日期字符串
 *  @return → 返回count天数前的日期字符串
 *  eg  :
 */
+ (NSString *)dateStringWithDaysBeforeNow:(int)count isShowHHmmss:(BOOL)isShowHHmmss;

/**
 *  @param  count 如果count == 7，则说明是7天前的日期字符串
 *  @desc → 获取count天数前的日期字符串
 *  @return → 返回count天数前的字符串
 *  eg  :
 */
+ (NSString *)dateStringWithDaysBeforeNow:(int)count;

/**
 *  @param  count 同上
 *  @param  isEnd 如果isEnd == YES, 则拼接23:59:59秒，否则拼接00:00:00
 *  @desc → 获取count天数前的日期字符串
 *  @return → 返回count天数前的日期字符串
 *  eg  :
 */
+ (NSString *)dateStringWithDaysBeforeNow:(int)count isEnd:(BOOL)isEnd;

/**
 比较两个日期的大小
 日期格式为:yyyy-MM-dd HH:mm:ss
 */
+ (int)compareDate:(NSString*)date01 withDate:(NSString*)date02 dateFormat:(NSString *)dateFormat;

/**
 *  与当前日期进行比较
 */
+ (int)compareNowDateWithDate:(NSString *)date dateFormat:(NSString *)dateFormat;

@end
